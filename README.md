# ISIC Archive Downloader
The ISIC Archive contains over 13k images of skin lesions, labeled as 'benign' or 'malignant'.
The archive can be found here:
https://isic-archive.com/#images

The current ways to download the database, provided by the ISIC foundation, which are known to me
are the following:
1. Downloading the images one by one via the Grider API provided in the site
2. Downloading the database using their isic-archive repository in github: 
   https://github.com/ImageMarkup/isic-archive
3. Download the database via the direct download button on their site.

The first option didn't seem feasible to us,
and we had problems with the second option.
The direct download in the third option never finished the downloaded successfully and always failed during the process.

We figured the direct download (which is the easiest and most comfortable way)
didn't work because the file was too big and if there is a connection problem
somewhere along the download process, the downloading process was stopped and hasn't resumed.

So instead of downloading the entire dataset at once, you could filter the images
to different sub-datasets using the filters on the website, and download each of the sub-datasets.

If you find the options above too laborious or unavailable like us, our script can help you.
We made a script that downloads the entire dataset automatically.

Here i'll explain the way the automatic download is available.
If you'd like, you can just skip to the instructions part and move on to download the dataset.

Searching for a few images using the Grider api, we found that the images are stored
at a url which is in the template of 'url_base_prefix + image_id + url_base_suffix'
and that their description are stored in 'url_base_prefix' + image_id'

So we wrote a script that, using the Grider API, found the ids of all the images
and downloaded the images and their description from the corresponding urls

You are most welcome to use the script with the simple instructions found below :)

We hope this script will allow researchers who had similliar difficulties
accessing ISIC's Archive dataset to have easier access and enable them to provide further work on this field,
as the ISIC foundation wishes :)


# Instructions
1. download or clone the repository
2. Open download_dataset.py and update the size parameter
   which is the number of images in the isic archive database
3. (optional) change the default images_dir and descs_dir which are the paths to the directories where the images and their descriptions will be downloaded.
   In addition you can also change the default amount of images each thread will download (thread_subset_size)
   but i don't think it's worth any bothering.
4. run download_dataset.py using ```python download_dataset.py```

# Note
   We assume that the images and descriptions have a specific url prefix and suffix as mentioned above.
   If the prefix or suffix ever change (and you start getting errors for example) - let us know and we will change it accordingly!
   You can let us know in the issues tab :)


# Finally: 
If you stumble into any issues - let us know in the issues section!

In addition, Any contributions of improvements to our code that will improve the comfort of the users 
will be dearly appreciated :)


# Written By
Oren Talmor & Gal Avineri

