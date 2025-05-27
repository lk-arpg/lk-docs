# How Random is Random?

Now... as with any use of RNG in games, users tend to treat distribution of rewards with suspicion, especially if they get a string of bad rolls. I decided it would probably be important to preemptively write this section to discuss the random number generation portion, as the same questions and issues tend to show up, and are often based on having only a partial understanding of random number generation.

As a disclaimer: I do not have in-depth knowledge of cryptography and cannot advise in that direction (which is out of the scope of this section, anyway).

!!! quote "The generated random numbers are not truly random. The results are predictable, given the right conditions."

Fact, but only half of the story.

!!! quote "For people to enjoy the game, numbers generated must use 100% cryptographically secure random number generation for fairness."

Myth, primarily regarding "fairness".

From these statements, we can see there are 2 separate issues that people are concerned with:

 1. That users with the technical knowledge may be able to exploit the system to their advantage
 2. That the numbers generated are inherently skewed in some way or the other so as to favour certain rolls

Let’s address these by looking at how numbers are rolled.

## How are random numbers generated?

Lorekeeper uses the built-in PHP function `mt_rand()` to generate numbers used for rolling rewards. The function uses the Mersenne Twister algorithm to generate numbers…which may be a familiar name if you play competitive Pokemon, as it's also the algorithm used in the game. For those who are unfamiliar: in the older versions of Pokemon, before features to make competitive battling accessible, serious players (and rare Pokemon collectors) would exploit the random number generation in the game to generate Pokemon with the exact stats and shininess they wanted. As you might realise... yes, this theoretically means you could do something similar.

There is a very big caveat, though, in that you need to have specific information in order to do it. In a Pokemon game, you have access to the entire game and your own game console. In a game running on someone else’s web server, a lot of the details are out of your reach.

Going a bit further into detail: random number generators, surprisingly, are not random. (Thus, they're more accurately called pseudo-random number generators.) An algorithm will always produce the same output given the same input. That’s one of the foundations of mathematics. It's how you can take someone’s Minecraft seed and generate exactly the same world on your computer. That concept, the “seed” is the important part - it’s the input that generates the predictable output, and if you know both the seed and algorithm, you can know the outcome.

How difficult is it to find the seed, then? Well, it happens that PHP's code is available online and the question has come up before. The seed value is a function of the current timestamp, the PHP process PID and a value produced by PHP's internal LCG.[^1] In simpler terms, anyone looking to exploit this would need 1. to know when exactly the number will be rolled, 2. to know some details that are known only to someone with access to the server/website setup, 3. a certain amount of data. 1 and 2 in particular are going to be unpredictable - the first requires knowing when exactly (to the second) your mods will approve a submission for example, and the second requires being able to run commands on your server (yikes!!!!!) and knowing how your loot tables are set up. Information could be gained from monitoring randomised data to reverse engineer some information about the MT - which, again, will probably tell nothing without knowledge of how the site data is set up.

I won't say it's entirely uncrackable - but if you do have someone with that amount of knowledge, determination and time to spend cracking your game, I feel you may have significantly bigger problems than game balance. Effectively speaking, in terms of monetary value of time vs monetary value of potential rewards to be gained, the odds that someone would jump through all these hoops to predict your game's rolls are extremely low.

## Fairness of Rolls

I don't think the actual issue is that people think the RNG is broken because it keeps rolling the same result. It's probably that it keeps rolling the same *negative* result. Nevertheless, the uniformity of rolls can be fairly easily verified: rolling a large enough pool of numbers and counting how often each one shows up will yield a spread that shows that none of them are significantly more likely to be rolled than any other.

The verification can be done by yourself in simple PHP - roll a million numbers from, say, 0 to 9 and output the counts. Paste this code [here](http://phptester.net/) for a quick test.

```php
$numbers = array_fill(0, 10, 0);
for ($i = 0; $i < 1000000; $i++) {
    $numbers[mt_rand(0, 9)]++;
}
foreach($numbers as $number=>$count) {
    echo "Rolled {$number}: {$count} times<br />";
}
```

Each number will be rolled close to 100000 times. The deviation is not particularly significant, and the significance decreases the more times you roll. On the other hand, the fewer times you roll, the more likely it is that you get results that look skewed.

The important thing to note is that someone rolling a bad result 10 times in a row is not indicative of the code being buggy - unlikely as 10 consecutive fails at a 50% rate is, a possibility is still a possibility. That's how probability works - if you roll bad results you're not necessarily due for something good in the near future, but in the big scheme of things, it'll even itself out eventually.

## Conclusion

In the context of a small game, for the purposes Lorekeeper was intended for, a cryptographically secure random number generator would not be noticeably better than PHP's built-in, non-cryptographically-secure `mt_rand()` if at all. Yes, the MT has its failings, and there are a number of very valid points on which it can be considered a "bad" pseudo-random number generator. However, just like in social situations, context is important, and in this context none of these points concern 1. your credit card number 2. any perceivable advantage someone may stand to gain in a reasonable amount of time with a reasonable amount of misguided effort. So, for our purposes... yes, the generated results are sufficiently random.

[^1]: [How is PHP's mt_rand seeded? - Stack Overflow](https://stackoverflow.com/questions/11358691/how-is-phps-mt-rand-seeded)