# Install Stuff For Deep Learning
Notes to install stuff need for Deep Learning. Maybe also other stuff as Latex, in case I get bored. 


Nvidia
======

Up to Feb 2018, I update to Cuda 9.0 (9.1 is not still compatible to everything)

### Driver Nvidia
* It is better to install Nvidia driver from Ubuntu repository to let it update automatically. In this way, upgrading ubuntu will, given the case, upgrade the driver without problem

```sudo apt-get install nvidiaXXX```

### CUDA & CUDNN
* To install CUDA library, download the BINARY -runfile(local) file from the Nvidia website:  
https://developer.nvidia.com/cuda-90-download-archive?target_os=Linux&target_arch=x86_64&target_distro=Ubuntu&target_version=1604&target_type=runfilelocal

* Give the file executable permisions, and execute it to install the library.  
```chmod +x cuda_9.0.176.1_linux.run```  
``` cuda_9.0.176.1_linux.run```   
**IMPORTANT:** when the installation ask you to install the driver, select **NO** (we do not want an static driver installation). You can select to do a symbolic link (would be under the name of cuda directly), or alternatively keep several cuda versions and link each framework directly to the desired one (to the folder cuda-X.X)

* Download CUDNN library from the Nvidia website (you need to be registered)  
https://developer.nvidia.com/cudnn  
Copy the files inside the cudnn lib64 folder to the corresponding cuda folder ```/usr/local/cuda-9.0/lib64```. 
Copy the files inside the cudnn include folder to the corresponding cuda folder ```/usr/local/cuda-9.0/include```. 



Pytorch in a Virtual Environment
======

* Create install and create the virtual environment  
```sudo apt-get install python-pip python-dev python-virtualenv```  
```mkdir ~/virtualenv/```  
* Launch a venv for pytorch and source it  
```virtualenv --system-site-packages ~/virtualenv/pytorch/```  
```source ~/virtualenv/pytorch/bin/activate```  
* Install pytorch stuff in the venv created  
```pip install numpy scipy matplotlib scikit-image scikit-learn ipython protobuf jupyter tqdm ipykernel```  
Get the link from the pytorch web (e.g options: linux, pip, python 2.7, cuda 9.0  
```pip install <link http://pytorch.org/>```  
```pip install torchvision```  
```python -m ipykernel install --user --name=numpy```  
* Add the path to bash  
```echo "alias pytorch='source ~/virtualenv/pytorch/bin/activate'" >> ~/.bashrc```  
```deactivate```  
* Execution  
**to activate:**   
```pytorch```  
**to deactivate:**  
```deactivate```


TensorFlow in a Virtual Environment
======

* Create install and create the virtual environment  
```sudo apt-get install python-pip python-dev python-virtualenv```  
```mkdir ~/virtualenv/```  
* Launch a venv for TensorFlow and source it  
```virtualenv --system-site-packages ~/virtualenv/tensorflow/```  
```source ~/virtualenv/tensorflow/bin/activate```  
* Install pytorch stuff in the venv created  
```pip install numpy scipy matplotlib scikit-image scikit-learn ipython protobuf jupyter tqdm ipykernel```  
```pip install tensorflow-gpu```  
```python -m ipykernel install --user --name=tensorflow```  
* Add the path to bash  
```echo "alias tensorflow='source ~/virtualenv/tensorflow/bin/activate'" >> ~/.bashrc```  
```deactivate```  
**to activate:**   
```tensorflow```  
**to deactivate:**  
```deactivate```



Get a Python-3 Virtual Environment
======

```sudo apt-get install python3-pip python3-dev python-virtualenv```  

```virtualenv --system-site-packages -p python3```  


Ubuntu Tweaks
======
```sudo apt install indicator-multiload```  
