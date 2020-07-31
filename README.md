# Arabidopsis Seed Detection

## 1. Anaconda, tensorflow(1.X) (version lower than 2.0) installation
  * For cpu version:
	`pip3 install anaconda`
	`pip3 install tensorflow==1.13.2`
  * For gpu version:
	`pip3 install tensorflow-gup==1.13.2`
## 2. Tensorflow object detection API installation
* [Installation instruction](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf1.md)
* Install models

	`git clone https://github.com/tensorflow/models.git`
* Python Package Installation

	* `cd models/research`
	* `protoc object_detection/protos/*.proto --python_out=.`
	** if can not compile protos, please replace research/object_detection/protos using my compiled [protos](https://github.com/FanruiMeng/Arabidopsis-Seed-Detection/tree/master/protos).
	* `cp object_detection/packages/tf1/setup.py .`
	* `python -m pip install .`
## 3. Create work directory 
	mkdir work_dir
## 4. copy graph_train, research, detect_noimage.ipynb, and mscoco_label_map.pbtxt into your work directory
	* if can not compile protos, please replace research/object_detection/protos using my compiled [protos](https://github.com/FanruiMeng/Arabidopsis-Seed-Detection/tree/master/protos).
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
