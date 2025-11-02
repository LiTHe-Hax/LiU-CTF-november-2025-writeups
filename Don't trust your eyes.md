at First if you look at the image, it seems like one of those AI generated images, that you have to squint your eyes to see the message. However, it says "It's not that easy", what a bummer!

then if you use exiftool on it on the comment part you see that says "It'sNotThisEither", then if you use steghide to extract the data with this command "steghide extract -sf image-1.jpeg" it will ask you for a passphrase. If you give it the comment in the image it will extract a text file with different image urls in it.

There are 327 lines in that file and 326 urls and 325 of them start with https. The one that does not start with https starts with oaawz. It seems it's been encrypted with Caesar cipher. If you decrypt that and follow that link you'll get at another image.

This one does not have any comments in it, and if you use steghide for it you don't have the passphrase. what if there are no passphrases for this one? if you just press enter it will extract an image for you. Unfortunately it is image of a troll :(.

in the description it is mentioned that the creator of this image likes 3D objects, and the title is "Don't trust your eyes", maybe they used stereograms.

if you use this tool https://piellardj.github.io/stereogram-solver/ you will see the flag