# Future Plans

These are ideas that are on the table for implementation in the future, should there be enough time for it. (Suggestions are not being accepted at this time, please refrain from asking for more features - I may ask in the future if that time comes, but for now there are already a lot of ideas to tackle)

## Communication Update

More communication features, eliminate the need to use any other sites/apps to reach other users.

#### User Side

- Messaging
- Comments
    - User page
    - Character page
    - News
    - etc.
- Forums - more below
- Blocking
- Reporting users/character profiles

#### Admin Side

- Features for managing comments
- Viewing users' block lists
- Reports queue

#### Forums

2 options:

- Manually built forums
- Use phpBB

Pros of manually-built forums:

- Easier to match the visual look
- Can do some features like responding in-character
- Definitely works with Laravel becaus... I'd be building it in Laravel

Cons of manually-built forums:

- Extremely tedious
- Everyone has different ideas of what features a forum should have

Pros of phpBB:

- Many existing modules that can be picked and chosen to match the site owner's needs
- More robust than what I can do due to community development over several years

Cons of phpBB:

- There are no complete instructions on integration with Laravel so this may be difficult

Ideally I'd like to go with the phpBB integration option but will have to spend a while tinkering with it to see how to make it work, the limitations, etc.

## Galleries/Text posts/Journals

Allow users to upload images and etc. on-site instead of relying on deviantART to host content.

Somewhat iffy on this one as it will rely on the site having enough storage space for images - but this will be the responsibility of the site owner I guess? ARPGs also tend to be small in scope so this should not prove to be a major problem...

- Galleries
    - Allow users to upload art (needs to be reportable for offensive content, any restrictions on content (must be ARPG-related, etc.) should be responsibility of the owner?)
    - Users can comment on uploaded pieces
    - Gallery pieces can be submitted as per normal for prompts, a prompt link is added on the page if it's accepted as a prompt submission
- Text posts
    - For hosting writing (reportable for offensive content as well)
    - Users can comment on uploaded posts
    - Can also be submitted for prompts, prompt link added if accepted as prompt submission
- Favouriting of art/text posts
    - Able to view your own favourites
    - Users can hide all of their own numbers/turn off notifs on people favouriting their works if they don't want to see them
- Journals
    - More or less same as text posts? But posted to a different place that's just like…Journal (maybe the name should be changed…something like Blog Posts or something, we're going back to 2003)
    - Can't be submitted, these are for casual use
    - Maybe polls…

## Watermarking

Built-in watermarking, ability to upload different watermarks, can also use for certing

- Create watermarks
    - Watermarks can have foreground and background layers
    - Background layer can have a "clipping mask" option - the character will be clipped to this layer if selected (this is to help with certing)
    - Either layer can be left blank if not needed - e.g. a simple semi-transparent foreground layer works as a traditional watermark, or opaque/elaborate foreground frame + background image can work as a decorated masterlist image
- Applying watermarks
    - Can select a default watermark that will be used for user uploads (in design approvals) - users will have to use this watermark
    - Mods with masterlist powers can select watermark (including in design approvals)
    - Watermark will always be applied in the centre, overlaid without changing opacity
    - Thumbnail generation?
        - Use watermarked art? Or non-watermarked? Or provide the option?
        - If it's watermarked it has to be a 2-step process to generate the image first, then crop the thumbnail
        - Maybe use a config option for this... groups that use full foreground/background certs will want to use the entire watermarked image, groups that use simple watermarking may want to use the unwatermarked and crop only the face, etc.
- Non-watermarked art
    - Non-watermarked art will only be accessible by masterlist staff/the current owner of the character
    - The URL of this art will change when the character changes hands, so the old owner will lose access (not a perfect solution, but probably helps)

## Misc

- Discord bot - probably in Python? commands to retrieve any public information from the site
- Oekaki BBS
    - html5 version of PaintBBS: https://github.com/funige/neo/
    - Sample usage: https://github.com/sakots/poti-kai
