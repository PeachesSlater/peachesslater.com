# PeachesSlater.com

A website for Peaches, based on [Photography](https://github.com/rampatra/photography). Forked from VioletRollergirl.com code. 

## Batch resizing images to thumbnails

1. Ensure you have [GraphicsMagick](http://www.graphicsmagick.org/) installed. On macOS, with Homebrew:
    ```shell
    brew install graphicsmagick
    ```
1. Drop your full size images into [the `images/gallery/fulls` directory](images/gallery/fulls).
1. Run the following shell snippet:
    ```shell
    for file in $(ls images/gallery/fulls); do
        gm convert -resize 512 images/gallery/fulls/$file images/gallery/thumbs/$file
    done
    ```

This script is suitable for running periodically, such as by placing it inside an executable file in any of the `/etc/periodic/*` directories configured for a `cron` daemon to run.
