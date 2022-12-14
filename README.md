# dlc-fun
Playing around with DeepLabCut and Bonsai for the Buenos Aires Hub of the course:
CAJAL Modern Aproaches to Behavioral Analysis 21-25 Nov 2022 from course directors Alexander Mathis and Dambee Kim
BA Hub was led by Sabri Benas, Ceci Herbert and Facu Ermina.

Follow the instructions for using DLC-live in Bonsai from:
https://github.com/bonsai-rx/deeplabcut
https://alexemg.github.io/DLC-Cajal-Course/content/Day3_DLClive.html
You will need to have installed Bonsai and the DLC packages and TensorFlow, have an exported model and the Bonsai workflow.
We added an overview in our hub slides 75-79 (Spanish): https://docs.google.com/presentation/d/1ke5zAIKqfNCteYBtaZEkyZeBlnWUPsr7f8k0jM4eMH0/edit?usp=sharing

Here is a primer about what you can do in Bonsai with this and how (learn more about using Bonsai at https://bonsai-rx.org/docs/articles/editor.html)
DLC-live is used in Bonsai for real time pose estimation (works best with GPU), to see and extract predicted body parts and use their positions to integrate with more Bonsai functionalities.
You can find two examples in this repository:
- a theremin controlled with one wrist moving up and down for pitch and another left to right for volume.
- a closed-loop task in which the nose of a mouse triggers a servomotor, LED and sound when close to an object.

0) A workflow (Bonsai program made from a series of interconnected nodes) is run with Start or F5. Data streams are processed from left to right. Nodes can be enabled or disabled for debugging.
1) Workflows can be edited when they are not running: in general, nodes have properties (click the node and find the window on the right to edit them).
In the CameraCapture node you will have to specify the camera's device ID.
In the PredictPose node you have to load the model and pose_config.
In the GetBodyPart node you can choose which body part you would like to extract, using the same name used for the labels in the model. You can use several GetBodyPart nodes to extract multiple bodyparts
2) Many nodes have visualizers which you can access by double-clicking a node while the workflow is running
In the case of CamaraCapture, you can see the camera feed.
In PredictPose you also see an overlay of the predicted bodyparts.
3) While the workflow is running, within a visualizer, with right click you access more options in a bar at the bottom of the window.
In PredictPose you can toggle DrawLabels to either see dots or dots with labels.
4) You can access the outputs of different nodes to build the workflow. While the workflow is not running, right-click the node and choose an output.
In the case of GetBodyPart, use Output > Position > X to get the X-position of that body part, for graphing, further signal processing or saving.
5) To save any data, you have to add a sink node to the workflow.
In the case of positions, you can use a CsvWriter node. Remember to set the properties of where it will be saved. If you want to save multiple positions in the same csv, you can use the Zip node before CsvWriter.

Have fun!
