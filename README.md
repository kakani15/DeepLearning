# Black and White Photo Colorization using CNN model

## Description of Dataset
Here COCO2017 dataset, short for Common Objects in Context, is used to train and test the model. This dataset is a large-
scale dataset widely used in computer vision as it contains images (RGB) that showcase objects in their natural context,
providing a diverse and rich collection for training and evaluating various AI models. There are three subsets, test2017 containing 40.7k image files, train2017 containing 118k image files
and val2017 containing 5,000 image files, and I chose the image files from subsets as the experimental dataset due to the
limited computation capacity, with a split rate of 0.2.

Source of the COCO2017 dataset: https://cocodataset.org/#download
Or it can be downloaded from https://www.kaggle.com/datasets/awsaf49/coco-2017-dataset

## Data Preprocessing
Since the image colorization model take grayscale images and then learn the features through various
convolutional filters, the original RGB images (ground truth images/real images) are converted to grayscale images, then
rescaled to a self-defined size, and normalized to a proper range before feeding to the model. To generate color
information basing on grayscale image (luminance information), the general practice is transforming RGB images to a
Lab color space and extracting the L channel (input) and the ab channels (target) (Figure 1), the generated color channels
will be concatenated with input before being converted back to RGB color images.

## CNN model results
The results are demonstrated through visualizations of image pairs, comparing the original color images with their grayscale counterparts. The `plot images` function facilitates the
side-by-side comparison of color and grayscale images, providing a qualitative assessment of the model's performance. For a sample set of five images, the visualization highlights the efficacy of the model in colorizing grayscale images, showcasing the transformation from monochromatic representations to vibrant, realistic color renditions. The color images, generated by the model, exhibit a coherent and visually appealing adaptation of hues and tones, effectively capturing the essence of the original scenes. Moreover, the resizing function is employed to preprocess images for both color and grayscale datasets. This function
standardizes the images to a uniform size (160x160 pixels) and ensures consistency in input dimensions for the CNN-based model. The resizing process involves converting images from the BGR format (as read by OpenCV) to RGB format and normalizing pixel values to a scale between 0 and 1. 
