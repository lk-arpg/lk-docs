# Developer Introduction

*The following is an introduction to Lorekeeper as project, and its ecosystem, aimed at those with a pre-existing technical background. For contribution guidelines, see [here](../contributing.md).*

The first and most important thing to understand about Lorekeeper is that it is not one single project; the "core" repository exists, but does not represent many (if any) sites which run it. To express it a different way, it is one project with a thousand forks, and work on it-- both on the core project and individual sites-- must keep this in mind.

Functionally, this is a consequence of the nature of the sites involved; each will want to have its own unique look and feel, tailored to the ARPG it hosts, and may have any number of features that have been developed as "extensions". In essence, each site is as much of a creative endeavor as it is a piece of software; while the core project provides the foundation, it is more or less expected that site operators make it their own.

## Extensions and Other Changes

There are many features that site operators might want for their ARPGs that aren't necessarily fit for inclusion in the core project. For instance, some features might fit a certain type of game but not others. In order to meet some of the more common needs (among other reasons), some members of the community have opted to write and publish additional features or modifications for core Lorekeeper. These are referred to as "extensions"; examples of these can be viewed on the [extensions wiki](https://wiki.lorekeeper.me/index.php?title=Category:Extensions).

From a technical perspective, however, Lorekeeper has no "plugin" support or similar. Instead, extensions are provided as git branches-- modified copies of core Lorekeeper that can be added to a given site by means of merging the branch with git. This process, as with any other site-specific modifications, often results in conflicts (including with updates to the core project). However, given the extensiveness of changes some sites may want to make, it would be difficult to create and maintain a sufficiently robust "plugin" system, if not impossible.

As a consequence, while you are free to do whatever you please to your own site, development environment, and so on, if you want to leverage the wealth of community-developed features and modifications you will want to maintain some amount of continuity with core Lorekeeper (on which extensions are based). For instance, significantly altering the formatting of code within the project is an easy way to create significant grief for yourself even without changing any functionality.

## Why/Why Not (Insert Tool Here)?

Occasionally we field questions as to why the project uses the particular tools it does-- PHP, blade files, Bootstrap, and so on-- rather than other frontend frameworks, including various "modern" JS frameworks. The short answer is that the project as it exists is already written, and to re-write it with any number of other tools would be prohibitively time- and labor-intensive for little to no benefit-- and have significant consequences for the broader ecosystem (extensions, individual sites, and so on) as well as demand existing contributors learn new tools in order to continue contributing. That time and energy is better spent improving the project.

### Docker

Docker in particular has come up a few times in the project's history, and it's a great tool-- if you yourself already have some technical background and are willing to deal with the additional layer of complexity that containerization, docker itself, etc. introduces.

For those without that background, "streamlining" set-up may make things more efficient in the short term, but introduces a variety of potential hurdles and does not adequately teach the fundamentals of working with the tools involved. Given that much more time is spent maintaining these sites than performing initial set-up, this misses the point of the exercise. Set-up is as much to provide an introduction to sysadmin tools and processes used as it is to arrive at a functional site-- knowlege and skills that will inevitably be necessary for site maintenance over time.