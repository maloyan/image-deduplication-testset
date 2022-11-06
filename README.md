# Image Deduplication - Testset

This is a test set for finding duplicates of images.
It consists of 177 query images and 12 nearest neighbors from our LAION-5B Clip image embedding index.
The images of a query & the 12 neighbors are in a folder with the name "1" for the first query, "2" for the second query, ... up until "177".


The downloaded and zipped image folders can be found here: [https://drive.google.com/file/d/1XidNj35sUuDestW39iOyiXk6P03ReQqs/view?usp=sharing](https://drive.google.com/file/d/1d0hxUFr4EAGGJlzzVCpfTy05CgZrrlgW/view?usp=share_link)

Some of the files are missing in the Gdrive zip file, cause trying to download them gave again and again failures. We advise to run all benchmarks on the zip file for consistency. Please make your scripts robuts for the case that some folders (42, 47, 75, 159) don't contain "query.zip" or that some neighbors are missing in a folder.   

Here can you find visualizations of the samples:
http://captions.christoph-schuhmann.de/visualizations-of-the-samples.html


The annotations are in a list of lists, where the first element is e.g. [0,0,1,1,0,0,0,1,1,1,1,1] and 0 means that it is non a duplicate and 1 that it is a duplicate.

As duplicates are considered images that show the same content from the same perspective, maybe with some slight crops, unimportant additional texts that don't change the meaning of the image, compression artefacts or slight blur, ... - If the same content is show from a different camera angle, it is not considered a duplicate.

Here is a Colab that benchmarks an ensemble based on CLIP L 14 & ResNet50 features: https://colab.research.google.com/drive/1uVZXaaG7clj_fYkMWTpkn9pp5t29Zm8-?usp=sharing

Results with Image Dedup https://github.com/idealo/imagededup :


<p align="center">
![image](https://user-images.githubusercontent.com/22318853/200183001-6fc032ad-1f91-449c-b128-b848deef9180.png)
![image](https://user-images.githubusercontent.com/22318853/200182960-bebc9999-191a-4cf0-8d7b-ae207d68cae8.png)
</p> 
