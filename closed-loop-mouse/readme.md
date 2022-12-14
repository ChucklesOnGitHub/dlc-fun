# Closed-loop mouse based on body part

In this example, when the mouse's nose was close to an object, then a servomotor, LED and sound would be triggered.
This was implemented as a threshold on the euclidean distance of the nose to the center of the object.

This is an addition on the workflow used for the lab practical “Closed-loop behavior with Bonsai” of the module “NEURAL SYSTEMS, COGNITION, GENOMICS & BEHAVIOR” of the “Latin American Training Program”. See full attribution and materials here: https://github.com/talleresopensource/latp-closed-loop-bonsai.

This was a refinement of the pixel tracking method used there, to try to only take into account more "active" exploration (head oriented towards the object).
This previous method was implemented with a threshold on "mouse pixels" entering a ROI around the object.
The previous method had false positive detections when the animal's body entered a region of interest.
This was resolved in the refined pose estimation method, which however needs some smoothing to account for noise in threhsold crossing and also runs much slower on a computer with CPU.

Specs used to run this DLC-live model in Bonsai (CPU only!)
Bonsai version: 2.7.1
DLC-live version (Bonsai.DeepLabCut): 0.3.0
TensorFlow for CPU: 2.6.0
Computer: 11th Gen Intel(R) Core(TM) i5-1135G7 @ 2.40GHz   2.42 GHz, 16 GB RAM, running 64-bit Windows 10 Pro

The mouse model was trained by me on this same computer with DLC 2.2 but just for testing purposes, for few frames and iterations. Would recommend getting one from the model zoo or training your own.
