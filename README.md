# Handwriting Template Processing
This project is the first step as part of a larger project.  
The purpose of this step is to separate the handwritten letters and sentences into their own collections in preparation for training an image classifier later on.

![Screenshot](screenshot.jpg)

### Operation
Run;  
```bash
# start your venv
python3 -m venv venv
source venv/bin/activate

# run the note book
jupyter notebook

# Then click on "Complete Process on Single Image.ipynb" to run the demo notebook
```

The steps are broken up into different files for ease of understanding.  
The steps below are the names of the notebooks that need to be run in order.  
Images need to be in ".jpg" format (taken care of in step 1).  

Steps:  
    1. setup and convert images to jpg  
        * src images in "./samples"  
        * saved in "./jpg" as grayscale images  
        * images are save in a different dir!!!  
    2. rotate images to landscape  
        * rotates the images in "./jpg"  
        * images rotated in-place  
    3. ensure pictures right-side up with template search  
        * need to automatically crop off the extra edges, margins  
        * reorients images in-place  
    4. crop off margins  
        * trims off the extra material in the images (extra text at bottom and whitespace margins)   
        * crops images in-place  
    5. downscale images  
        * images are of high resolution in case I need the extra detail in the future.  
        * need to reduce their sizes going forward to prepare for the classification algorithms.  
        * images are downscaled in-place  
    6. deskew images  
        * deskewing images works better on lower resolution images than the originals  
        * images are deskewd in-place  
    7. slice the images into 8 parts  
        * the 8 major sections;  
            * uppercase  
            * lowercase  
            * digits  
            * punctuation  
            * sent1  
            * sent2  
            * sent3  
            * sent4  
        * images are saved in a different dir!!!  
        * images are put in "./major_sections/" followed by their section name and file name  
            * ex: "./major_sections/uppercase/1.jpg"  
    8. extract individual boxes  
