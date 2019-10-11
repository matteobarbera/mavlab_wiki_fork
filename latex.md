# Latex Tips
This page hosts some random tips when working with latex for conference/journal submissions.

## PDF diff (Linux)
It is often useful to show the changes made when submitting a revision for a paper, here we show you a script to automatically compile this for you. *Latexdiff* is a package which compares two latex files and produces a third latex file which, once compiled, will generate a file markup showing removed text in red and added text in blue.

Firstly you need to install the latexdiff package by running the following command in the terminal (if you're copying the line, remember you need to use *Ctrl+Shift+v' to paste into the terminal):

```
sudo apt-get update && sudo apt-get install latexdiff
```

Copy the following script in a file called *diff.sh* in the same folder as the *main.tex* for the project you want to compare.

``` 
#!/bin/bash

if   [ ! -d "$1" ]; then
	echo "please enter a valid directory";
    exit 1
fi

if   [ ! -d "changes" ]; then
	mkdir changes
fi

files=('*.tex')
for file in ${files[@]}; do
	latexdiff --math-markup=0 $1${file} ${file} > changes/${file}
done

#latexdiff --math-markup=0 $1main.tex main.tex > changes/main.tex
```

Make the file executable by typing `sudo chmod +x diff.sh` in the terminal. You can now run the script with `./diff.sh prev_version_folder`.

Replace *prev_version_folder* with the past to your previous version. The script assumes that you have all your *.tex* files in the same folder as your *main.tex*, if this is not the case, you can edit the line `files=('*.tex')' to 'files=('sub_folder/*.tex')` with your correct *sub_folder* name. You can copy and paste that section if you have several sub-folders. You will also have to uncomment the last line of code to ensure your *main* is still included. You must have the same relative file structure in your two versions for this script to work correctly.

Once you have successfully run the script, you can build the *.tex* files in the folder *changes*. You will have to copy your pictures into that folder for them to be included. Alternatively you can change the graphics path (but then you will have to do this every time you run the diff script.

## Gray-scale PDF (Linux)
Many journals have print versions in gray-scale only and require that images are legible without color. The following script will convert a color PDF to a gray-scale PDF to help visualize if there are any issues with your images. I suggest copying the following into a filed called *2grayscale.sh*.

```
#!/bin/bash

gs \
 -sOutputFile=$1gray.pdf \
 -sDEVICE=pdfwrite \
 -sColorConversionStrategy=Gray \
 -dProcessColorModel=/DeviceGray \
 -dCompatibilityLevel=1.4 \
 -dNOPAUSE \
 -dBATCH \
 $1
```

Again, make the file executable `sudo chmod +x 2grayscale.sh` and run int `./2grayscale file_path.pdf`

## Some notes on working with scripts (Linux)
If you find yourself using scripts a lot and/or find it inconvenient to always copy the script files or type out long file paths, you might want to store all your scripts in one location and make them accessible from anywhere. A common location to store scripts is a *bin* folder in your home directory (i.e. *~/bin/*). Ubuntu (and Debian based distributions) automatically add this folder to the PATH if it exists. You can verify this by looking for
```
# set PATH so it includes user's private bin if it exists
if [ -d "$HOME/bin" ] ; then
    PATH="$HOME/bin:$PATH"
fi
```

in the (hidden) file *~/.profile*. Any script in this folder is then accessible from any directory. For the example of *2greyscale.sh*, instead of placing the script in the same folder as your pdf or typing out the whole file path `./2grayscale file_path.pdf`, you can place the script in *~/bin/*, open the terminal at the location of your pdf and simply type `2grayscale file_name.pdf`.

*Note: If you're placing your scripts in a central location, make sure the script names don't conflict with other terminal commands!*