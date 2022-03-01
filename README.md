# ai_mask_detector
A deep neural network for detecting mask status. Uses NVIDIA Jetson Nano.

## SETUP AND EXECUTION
1. First, make sure you have a Jetson Nano kit: https://developer.nvidia.com/embedded/jetson-nano-developer-kit

2. Set up your Jetson Nano according to the instructions of the kit.

3. This project was done via JupyterLab for ease of use. Install the following Python packages to your JupyterLab environment. Keep in mind that this is a comprehensive list, and you probably already have most of these in your environment. Blog tutorial for installing packages from Jupyter: https://jakevdp.github.io/blog/2017/12/05/installing-python-packages-from-jupyter/

	Python Packages:
		torch, 
		jetcam, 
		torchvision, 
		glob, 
		PIL, 
		subprocess, 
		cv2, 
		os, 
		uuid, 
		numpy, 
		traitlets, 
		threading, 
		time

	JupyterLab Specific Packages:
		ipywidgets

4. Download the code from this repository and open it in JupyterLab. Alternatively, the code can be easily adapted for other environment, although the widgets would need to be redone.

5. Load notebook and code into JupyterLab.

6. In the first block, uncomment the appropriate camera that you are using. 

7. Run all blocks except the final one. Please be patient and wait for the confirmation text below the block to make sure everything runs properly.

8. In the final block, uncomment the appropriate view you want. In the setup process, you may want to collect data and train the model on your setup. To do so, see "Uncomment code below for training interface" in the code. Alternatively, feel free to any data you have previously recorded. I recommend at least 100 photos for each category.

NOTE: If you wish to capture multiple datasets, you can add more datasets to the second block. For instance: DATASETS = ['ds_0', 'ds_1', 'ds_2'] 

9. Once you have your data, type in 20 for epochs, and hit train. Do not worry if you don't see any progress immediately, the first epoch is always the slowest.

10. Once the model is trained, feel free to save it. In the final block again, re-comment the code for training interface, and uncomment the code for results interface. Run the block, right click, and hit "Create New View For Output".

11. Now your program should be ready to go! Hit "Live" and see for yourself.

## CUSTOMIZING OUTPUT CHANNELS
Currently, the code gives you a text message depending on the status of your masking. However, you could customize this output to do whatever you want! For instance, you could have it snap a photo of any person without a mask, or have a speaker system that tells them to put on a mask (or fix their mask, depending on their masking status).

In the 6th code block, there are two things you can easily change. First, the weight requirement for sufficient confidence in the detected masking status is currently 0.5, or 50%. You can change this if you'd like, but remember to only use numbers 50% and up. Otherwise, multiple categories can have sufficient confidence. Second, see the code under the comments for no mask, bad mask, good mask, and undecided. Currently, these is a simple warning_widget that changes its text depending on masking status. Here, you can make masking status do whatever you want.  
