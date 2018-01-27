# batch-jpg-to-webp
Batch convert JPG to WebP in Ubuntu Command line


First install the webp converter by this

```sudo apt-get install webp```


go inside the directory where all images are there
make sure all images are in RGB color mode, otherwise you will get error for CMYK images.
Convert all images to RGB by this command (you should install ImageMagik to do that)

```for f in *.jpg; do convert -colorspace RGB "$f" "${f}"; done```

finally convert all images to Webp format

```for f in *.jpg; do cwebp -q 90 "$f" -o "${f}".webp; done```

Now you have filename.jpg.webp beside  filename.jpg for all your images.
You can set the nginx or other webservers to conditionally show webp instead of jpg if browser support 
Read this page to setup it in nginx config : https://github.com/uhop/grunt-tight-sprite/wiki/Recipe:-serve-WebP-with-nginx-conditionally

I have also create a gist here  : https://gist.github.com/ahadyekta/8803818246f0aefe3a6a3a989a3a7804
