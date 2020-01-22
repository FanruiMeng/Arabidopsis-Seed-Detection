# Arabidopsis-Seed-Detection
1. install anaconda, tensorflow(version lower than 2.0)
	pip3 install anaconda
	pip3 install tensorflow==1.15
2. downlow the tensorflow models 
	https://github.com/tensorflow/models
	unzip models
3. create a work directory 
4. copy graph_train, research directory under models directory, detect_noimage.ipynb, and mscoco_label_map.pbtxt into your work directory
5. replace research/object_detection/protos use already compiled protos.
6. create a test_image directory at your work directory, and copy your images to test_images directory
7. assign the home directory for jupyter
	a. generate jupyter config file
		jupyter-notebook --generate-config 
	b. go to config file change home directory to your work directory
		c.NotebookApp.notebook_dir = 'your work directory'
8. run detect_noimage.ipynb at jupyter-notebook
