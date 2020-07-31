# Arabidopsis Seed Detection

## 1. install anaconda, tensorflow(1.X) (version lower than 2.0)
  * For cpu version:
	`pip3 install anaconda`
	`pip3 install tensorflow==1.13.2`
  * For gpu version:
	`pip3 install tensorflow-gup==1.13.2`
## 2. Tensorflow object detection API installation
	[Installation instruction](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf1.md)
	* Install models
	`git clone https://github.com/tensorflow/models.git`
3. create a work directory 
4. copy graph_train, research, detect_noimage.ipynb, and mscoco_label_map.pbtxt into your work directory
5. replace research/object_detection/protos use my compiled protos(download from my github).
6. create a test_image directory at your work directory, and copy your images to test_images directory
7. assign the home directory for jupyter
	A. generate jupyter config file
		jupyter-notebook --generate-config 
	B. go to config file change home directory to your work directory, like below:
		c.NotebookApp.notebook_dir = 'your work directory'
8. split scanned images into single plate.
   python 00_1_split_scan_images.py
9. run detect_noimage.ipynb at jupyter-notebook
#If you want to save the results images, please use detect_save_image_results.ipynb
