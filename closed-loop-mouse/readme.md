# Closed-loop mouse based on body part

In this example, pose estimation is used to get the mouse's nose and detect when the nose is close to an object. This was implemented as a threshold on the euclidean distance of the nose to the center of the object.

Two workflows are provided:
- closed-loop_live_demo.bonsai
When the mouse's nose was close to an object, then a servomotor, LED and sound are triggered.
This is an addition on the workflow used for the lab practical “Closed-loop behavior with Bonsai” of the module “NEURAL SYSTEMS, COGNITION, GENOMICS & BEHAVIOR” of the “Latin American Training Program”. See full attribution and materials here: https://github.com/talleresopensource/latp-closed-loop-bonsai.

- closed-loop_live_demo_comparison.bonsai
Implements both the refined method with pose estimation and the original pixel detection method. This previous method was implemented with a threshold on "mouse pixels" entering a ROI around the object.
The previous method had false positive "object intraction" detections when the animal's body entered the region of interest instead of inspecting the object. This was resolved in the refined pose estimation method, which takes into account more "active" exploration (head oriented towards the object), and could be further refined with smoothing or time of orientation towards object.

We discuss pose estimation as a refinement of the pixel detection method or centroid tracking in cases where it really can provide an advantage, considering the tradeoff of effort in training models and computational power for online inference.

Specs used to run this DLC-live model in Bonsai (even with just a CPU!)
Bonsai version: 2.7.1 and 2.9.0
DLC-live version (Bonsai.DeepLabCut): 0.3.0
TensorFlow for CPU: 2.6.0
Computer: 11th Gen Intel(R) Core(TM) i5-1135G7 @ 2.40GHz   2.42 GHz, 16 GB RAM, running 64-bit Windows 10 Pro

The mouse model in this repo was trained by me on this same computer with DLC 2.2 but just for testing purposes, for few frames and iterations. Works great on CPU to quickly demo DLC-live in Bonsai for students.

An alternative would is to get the top-view mouse SuperAnimal made by [Ye et al 2023]((https://arxiv.org/abs/2203.07436v2) in the [DLC_ma_supertopview5k_resnet_50_iteration-0_shuffle-1.tar.gz
]([url](https://huggingface.co/mwmathis/DeepLabCutModelZoo-SuperAnimal-TopViewMouse/tree/main)) and running it with a GPU. This generalizes well and worked really nicely even with a 3D printed mouse. Having a live camera stream gets the point across better than using a file, which feels too similar to offline inference.

You would also train your own model for specific applications.
