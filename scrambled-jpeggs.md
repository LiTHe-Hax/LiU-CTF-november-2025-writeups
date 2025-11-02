The source code contains two Python modules `main.py` and `image.pyc`. The latter is a _compiled_ Python module and you'll have to decompile it in order to figure out how to descramble the image. You can use the website [Pylingual.io](https://pylingual.io/) to decompile it. Save the decompiled as `image.py` in the same place as `image.pyc` and delete the latter.

If you look inside `image.py` you'll see a function called `scramble_img`, which loops over every pixel in an image and scrambles them. If you simply reverse the order of the for loop, the program will instead descramble the image. In other words, the for loop should look like this:

```{py}
for row, col in reversed(list(itertools.product(range(row_count), range(col_count)))):
```

After you've saved the changes, you can descramble the image with the following commands:

```{bash}
pip install opencv-python opensimplex
python main.py <PATH_TO_THE_IMAGE>
```

Now there should be another image in the same directory as the scrambled image, which should contain the flag!
