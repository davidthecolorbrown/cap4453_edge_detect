# assignment 1 - elementary edge detection (module 1)
* objective: 
* chess picture images: http://www.cs.ucf.edu/courses/cap4453/inputpics,
* sobel.c base program: http://www.cs.ucf.edu/courses/cap4453/progs

## pgm format
* header info: details image file type (P5), image size (width/height, 256 each), max intensity value (255).
* body: 2D array holding the integer (stored as char) pixel values representing intensity (or color) for each row/col in image
    * 0 value for intesity: black
    * 255 value for intensity: white
    * everything inbetween is a tone of gray
    * each pixel value is a single 1-byte integer stored as a char

## instructions
* download sobel.c
* run sobel.c using "face05.pgm"
* add code to make sobel.c use thresholds (Hi threshold, Lo threshold)
* add three lines of code to generate header for .pgm viewer (http://www.cs.ucf.edu/courses/cap4453/progs/rawtopgm.)
* run new program and make sure it can be viewed in pgm viewer, three outputs;
    1) magnitude image
    2) output due to hi threshold
    3) output due to low threshold
* run on chess image (garb34.pgm) and get three output images which should approximately match output from www.cs.ucf.edu/courses/cap4453/outputpics
    1) magnitude image (sobelmag.pgm)
    2) output due to hi threshold (sobelout1.pgm)
    3) output due to low threshold (sobelout2.pgm)
* submit sobel.c code 
## random notes i've managed to forget about C
* command-line args
    * argc: number of args passed
    * argv[]: pointer array pointing to each arg passed to program (argv[0] == name of program itself)
    ```bash
    $ ./program.out argv[1] argv[2] .... argv[argc] // argv[0] == 'program.out'
    ```
* compiling C program
    ```bash
    # compile with gcc
    gcc program_name.c -o program_name
    # execute
    ./program_name argv[1] argv[2] 
    ```
* command-line arg for running program:
```bash
# sobel.c with single threshold
./sobel input_img.pgm output_img.pgm threshold
# sobel.c with low/high threshold
./sobel input_img.pgm output_img.pgm low_threshold high_threshold
# sobel.c with three outputs + low/high threshold
./sobel input_img.pgm mag_out.pgm low_out.pgm hi_out.pgm low_threshold high_threshold
# output for face05.pgm
./sobel face05.pgm sobelmag.pgm sobelout1.pgm sobelout2.pgm 40 110
# output for garb34.pgm
./sobel garb34.pgm sobel_out.pgm sobel_low.pgm sobel_hi.pgm 40 110
```

git push -u origin main
