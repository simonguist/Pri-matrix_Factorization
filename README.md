# Training I3D models on the Chimp&See dataset

Competition entry (5th place) for the DrivenData Pri-matrix Factoriation competition. Based on Inflated 3D ConvNet (I3D) models.

Find out more about the competition [here](https://www.drivendata.org/competitions/49/deep-learning-camera-trap-animals/).


### Main dependencies:
tensorflow, ffmpeg, sk-video, tqdm, dm-sonnet  
  
For example, if you want to train on AWS you can choose as AMI `Deep Learning AMI with Source Code (CUDA 8, Ubuntu)` or `Deep Learning AMI with Source Code (CUDA 9, Ubuntu)` and run the following commands to install remaining packages:  
`$ sudo apt-get install ffmpeg`  
`$ sudo pip3 install sk-video`  
`$ sudo pip3 install tqdm`  
`$ sudo pip3 install dm-sonnet`  
`$ sudo ldconfig /usr/local/cuda/lib64  #Resolve cuda import error`

### Instructions:
- Download raw data, submission format and training set labels from [Drivendata](https://www.drivendata.org/competitions/49/deep-learning-camera-trap-animals/data/)
- Get the trained RGB-I3D ImageNet model from [Deepmind](https://github.com/deepmind/kinetics-i3d)
- Convert videos from raw data to fixed resolution of 224x224. You can use the `convert_videos` function in `primatrix_dataset_utils.py`
- Modify hyperparameters and local paths in `train.ipynb` and then run it to train the model

### Sources:
Carreira, Joao, and Andrew Zisserman. "Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset." arXiv preprint arXiv:1705.07750 (2017). Code and trained models: https://github.com/deepmind/kinetics-i3d
