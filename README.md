# Cartoonize LinkedIn Photo

In our post [Fun With Numpy](https://crawstat.com/2020/10/09/fun-with-numpy-image-processing/) from a few months ago, we loaded a color photo, converted it to a 3D pixel array, and edited it simply using numpy. 

I recently came across a post on [cartoonizing a photo](https://towardsdatascience.com/turn-photos-into-cartoons-using-python-bb1a9f578a7e) with python using cv2 and numpy and tried it out to cartoonize my LinkedIn profile photo. It follows two core principles underlying a cartoon:

1) Sharper, more pronounced edges 
<br>2) Fewer, more homogeneous colors 

We'll detect edges by defining a function that converts to grayscale, reduces noise, and uses cv2.adaptiveThreshold to detect edges. We'll reduce color palette using K-means clustering, setting the number of clusters to 7. We'll soften using cv2.bilateralFilter, which smooths flat regions while keeping edges sharp. Lastly, we'll combine the edge and color effects using bitwise_and and compare our original and final cartoon images. Here's our notebook on [Google Colab](https://colab.research.google.com/drive/17YOeVmsCNKMIVWNNWAP4eubkPH3YbygT?usp=sharing&authuser=1) and Git. Try it out on your own photo! 
