## Theremin

Adapted from the example here: https://alexemg.github.io/DLC-Cajal-Course/content/Day3_DLClive.html

Using a webcam, move one wrist up and down to control sound frequency (pitch) and the other left and right to control sound amplitude (volume).
On a CPU this has a few seconds lag but it makes making melodies with your body even more fun :D

The activity is easier to understand if the PredictPose visualizer is open (double-click that node while the workflow is running) and showing the body part labels (right-click the window and select Draw Labels). Then, also double click on both Rescale nodes to see the graphs and have a reference for the coordinates of the body parts that are creating the sound.

Start by calibrating the Rescale max and min to be within the camera boundaries and around the coordinates in which the body parts usually are. To do this, hover over the visualizer to check the cursor coordinates and roughly map the ranges you want to capture. You can also modify the ranges of the waveform amplitude and frequency to control the range of sound volume and pitch. And you can also of course change the body parts that make the sounds!

Specs used to run this DLC-live model in Bonsai (CPU only!)
Bonsai version: 2.7.1
DLC-live version (Bonsai.DeepLabCut): 0.3.0
TensorFlow for CPU: 2.6.0
Computer: 11th Gen Intel(R) Core(TM) i5-1135G7 @ 2.40GHz   2.42 GHz, 16 GB RAM, running 64-bit Windows 10 Pro

Human model provided by Sabrina Benas who downloaded it from the model zoo some time in 2022:
https://drive.google.com/file/d/1U9moI0B4jCpBEPRvnPhRBPb11GAbPqyg/view?usp=share_link
Probably originally from Insafutdinov, Eldar, et al. 2018	arXiv:1605.03170 

DeepLabCut: Mathis et al. 2018
Model Zoo: http://modelzoo.deeplabcut.org
