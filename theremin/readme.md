# Theremin

Project by Ceci Herbert adapted from the example here: https://alexemg.github.io/DLC-Cajal-Course/content/Day3_DLClive.html

Using a webcam, move one wrist up and down to control sound frequency (pitch) and the other left and right to control sound amplitude (volume).
On a CPU this has a few seconds lag but it makes making melodies with your body even more fun :D

The activity is easier to understand if the PredictPose visualizer is open (double-click that node while the workflow is running) and showing the body part labels (right-click the window and select Draw Labels). Then, also double click on both Rescale nodes to see the graphs and have a reference for the coordinates of the body parts that are creating the sound.

Start by calibrating the Rescale max and min to be within the camera boundaries and around the coordinates in which the body parts usually are. To do this, hover over the visualizer to check the cursor coordinates and roughly map the ranges you want to capture. You can also modify the ranges of the waveform amplitude and frequency to control the range of sound volume and pitch. And you can also of course change the body parts that make the sounds!

## Versions
- Theremin.bonsai
First used as a demo of DLC-live in Bonsai for the Buenos Aires hub of the Cajal Advance Neuroscience Course on Modern Aproaches to Behavioral Analysis (21-25th Nov 2022) Video: theremin_argentino.mp4

- Theremin_piano_threshold.bonsai
The piano mapping and start control were added for an activity in the Cultural Science Center C3 in Buenos Aires (25th Feb 2023) with Sabri, Salva and Ulises.

- Theremin_movenet_withcontrollogic_multicast.bonsai
For upcoming presentations the toggle control logic was added to allow for standalone use of the activity. This was done with the help of Bruno Cruz from NeuroGears (Bonsai developers). https://github.com/bonsai-rx/bonsai/discussions/1278. And also used MoveNet as an alternative to DeepLabCut.

We have many ideas on how to expand the project. 

Share how you used it and I can add it here!

## Coming soon: project future, more documentation and videos.

## Specs

Specs used to run this DLC-live model in Bonsai with CPU only
Bonsai version: 2.7.1
DLC-live version (Bonsai.DeepLabCut): 0.3.0
TensorFlow for CPU: 2.6.0
Computer: 11th Gen Intel(R) Core(TM) i5-1135G7 @ 2.40GHz   2.42 GHz, 16 GB RAM, running 64-bit Windows 10 Pro

For GPU I have tested it with
Computer: 11th Gen Intel(R) Core(TM) i5-1135G7 @ 2.40GHz   2.42 GHz, 16 GB RAM, running 64-bit Windows 10 Pro
Nvidia GEFORCE GTX 1650 Ti
CUDA 11.2 cuDNN v8.1.0
TensorFlow for GPU: 2.10.0
Bonsai version: 2.7.2
DLC-live version (Bonsai.DeepLabCut): 0.3.0

Human model provided by Sabrina Benas who downloaded it from the model zoo some time in 2022:
https://drive.google.com/file/d/1U9moI0B4jCpBEPRvnPhRBPb11GAbPqyg/view?usp=share_link
Probably originally from Insafutdinov, Eldar, et al. 2018	arXiv:1605.03170 

DeepLabCut: Mathis et al. 2018
Model Zoo: http://modelzoo.deeplabcut.org

MoveNet implementation in Bonsai by Bruno Cruz https://github.com/bruno-f-cruz/movenet
