# How to exit vim

When entering you can find a home folder for torbjorn and enter it. In it there is a text about the-ant transcribed from the brilliant exurb1a and a folder named chroot.

in the chroot folder you will find a very similar system with the difference that there is no chroot and the home folder of bjorntor is there. The the-ant ant text is there in a similar way as well.

If you read the-ant the story sums up as a human sitting and reading a book and an ant asks what the book is for, for the ant can't comprehend the writing because he is so small. After trying to explain the concept of a book to an ant he realizes that he himself is small and asks the world around him what the world is for and a greater voice answers him.

If you look at the hidden files in torbjorns home folder there is also a .vimrc present which will chroot into the chroot folder.

You can run
```bash 
su torbjorn; vim ~/The-Ant.txt
```

and instead of reading the text, you will find yourself in a new root of the bjorntor user. This coupled with the text can make you realize that you also are chrooted from the moment you logged in. Next step is to find that if you exit the chroot, vim also exits. Unless you exit with an error code, then vim is preserved.

run exit 1 and you will find a spooky ghost but remain in vim instead of exiting from the whole ssh session. From within vim you can run :!bash to get a shell or simply :!cat /flag.txt

