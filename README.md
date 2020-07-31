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
	* `protoc object_detection/protos/*.proto --python_out=.` #NOTE: if can not compile protos, please replace research/object_detection/protos using my compiled [protos](https://github.com/FanruiMeng/Arabidopsis-Seed-Detection/tree/master/protos).
	* `cp object_detection/packages/tf1/setup.py .`
	* `python -m pip install .`
## 3. Create work directory 
	mkdir work_dir
	cp graph_train models/research mscoco_label_map.pbtxt work_dir

## 4. Seed detection using trained model
### Jupyter:
* Assign home directory for jupyter

	A. Generate jupyter config file
	
		jupyter-notebook --generate-config
	B. Change home directory to work directory in config file:
	
		c.NotebookApp.notebook_dir = 'work_dir'
		
* split scanned images into single plate.

   `python 00_1_split_scan_images.py`
   
* run detect_noimage.ipynb at jupyter-notebook

#If you want to save the results images, please use detect_save_image_results.ipynb
### Terminal 
 * `base_path`: the absolute path including graph_train director
 * `test_images`: test images directory
 * `python detect.py --base_path=work_dir --test_images=test_image` Or
 * `python detect_save_image_results.py --base_path=work_dir --test_images=test_image`
