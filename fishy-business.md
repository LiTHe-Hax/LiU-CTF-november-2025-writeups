# Fishy business

There are a lot of folders in a tree structure in the users homefolder. At the bottom of every path there is an image called herring.png which is a red herring. In one of these folders another not_herring.png is placed.

The user has to figure out that herring is of no importance and try to look for everything that is not herring.png.

one might use 

```bash
find . -type f
```

to find all the files in the nothing-fishy folder but there are so many herrings so you need to filter them out.

```bash
find . -type f | rev | cut -d '/' -f 1 sort -u | rev
```

this will inform you that a not_herring exists in the system so you can narrow your search down 

```bash
find . -name "not_herring.png"
```

will give you the path to not_herring

copy it to your local machine using scp and open in gimp.

The image is white except for the herring and the flag. The flag is in colour #fefefe. You can use the fill tool with a tolerance of 0 to extract the flag, or use brightness and contrast sliders to find it.
