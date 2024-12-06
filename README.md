# DeepLesion-YOLOv3
An experimental application of the YOLOv3 model on DeepLesion for lesion detection. The model's architecture was designed based off of the architecture table presented in the [YOLOv3 paper](https://arxiv.org/pdf/1804.02767) with slight modifications (extra convolution and residual layers) to downsize the 512x512 images in the dataset to the 256x256 images which the YOLOv3 model in the paper was built to handle. 

This model has only been tested on the DeepLesion subset from kaggle, where it has been prone to overfitting and poor generalization to new images. It's possible that the model will have better results when trained on the entirety of the DeepLesion dataset, but a proper computational setup and likely some modification to the data handling code will be required.

## Dataset
See https://www.kaggle.com/datasets/kmader/nih-deeplesion-subset for downloading a small subset of the DeepLesion dataset (~8GB)

See https://nihcc.app.box.com/v/DeepLesion for downloading the entire DeepLesion dataset (>200GB)

## Using your GPU on the model
If you wish to train the model on your GPU (recommended), see https://pytorch.org/get-started/locally/ to install pytorch with GPU support.

## To run

First, make sure you've downloaded your dataset and it's structured correctly for training. DL_info.csv and a folder named "images" should be in the same directory as the ipynb. "images" should contain all the folders of CT scan images and those folders will be named like "000001_01_01" and be full of images with names like "103.png". 

Your directory tree should look something like this:

DeepLesion-YOLOv3/\
├─ DeepLesion-YOLOv3-torch.ipynb\
├─ DL_info.csv\
├─ images/\
│  ├─ 000001_01_01/\
│  │  ├─ 103.png\
│  │  ├─ 104.png\
│  ├─ 000001_01_02/\
│  │  ├─ 008.png

A couple images are provided in the repo for you to see how the data should be structured - feel free to override them.

Secondly, you'll need the required libraries to run the code. Use
```bash
python -m pip install requirements.txt
```
to install them.

You can now proceed to run through the cells in DeepLesion-YOLOv3-torch.ipynb.
