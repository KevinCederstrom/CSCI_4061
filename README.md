# CSCI_4061
CSCI4061 Kevin Cederstrom and Xinkai Wang
#!/bin/csh 

set input=$argv[1]
set output=$argv[2]

if (! -d $output) then
mkdir output
else
echo "$output already exists"
endif

find $input -name "*.tiff" -exec cp {} $output \;
find $input -name "*.jpg" -exec cp {} $output \;
find $input -name "*.PNG" -exec cp {} $output \;
find $input -name "*.gif" -exec cp {} $output \;

mogrify -format jpg $output/*.tiff
##mogrify -format jpg $output/*.png
mogrify -format jpg $output/*.gif

rm -f $output/*.tiff
##rm -f $output/*.png
rm -f $output/*gif



##convert -thumbnail 200x200 *.jpg

echo $input
echo $output


