# Problem Description
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
The task of detecting and tracking multiple objects in real-time video streams or images presents a complex challenge in computer vision applications. Traditional computer vision methods often struggle with accuracy and efficiency when faced with diverse object types, occlusions, and dynamic scenes. To address this, the combination of YOLOv7 (You Only Look Once) for object detection and SORT (Simple Online and Realtime Tracking) for multiple object tracking emerges as a powerful solution.

## Challenges
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
1.  __Accurate Object Detection:__ Traditional object detection methods may fall short in accurately identifying and localizing objects, particularly in cluttered or crowded scenes.
Existing solutions might lack the precision needed to discern object boundaries and classes effectively.

2.  __Continuous Object Tracking:__ Maintaining consistent tracking across frames becomes challenging due to factors such as occlusions, abrupt changes in object appearance, and variations in object motion.

3.  __Real-time Processing:__ Achieving real-time performance in processing video streams or images is crucial for applications like video surveillance, autonomous vehicles, and robotics.
Traditional methods may struggle to meet the computational demands of these real-time scenarios.
  

# Project Overview
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## Input 
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
![image](https://github.com/Mahi4052/Multiple-Object-Detection-Tracking-Counting/assets/95848665/769fadd3-a130-44d5-aed8-18425a2528b4)


## Detection
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
1.  __YOLOv7 (detector):__ This state-of-the-art object detection model receives the input image or video frame.
   
2.  __Analysis:__ YOLOv7 analyzes the input using convolutional neural networks and predicts bounding boxes around objects it identifies, along with their class probabilities (e.g., person, car, dog).
  
3.  __Output:__ YOLOv7 outputs a list of detections containing bounding box coordinates, object class, and confidence score for each identified object.


## Tracking
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
1.  __SORT (tracker):__ This multi-object tracking algorithm takes the detections from YOLOv7 as input.
  
2.  __Association:__ SORT uses a Hungarian algorithm to associate detections from the current frame with tracks from the previous frame. This association considers factors like location, appearance (bounding box size), and motion trajectory.

3.  __Track creation/maintenance:__

    3.1  __New tracks:__ If a detection cannot be associated with an existing track, SORT creates a new track for it.

    3.2  __Track update:__ For existing tracks, SORT updates their positions and bounding boxes based on the associated detections.

    3.3  __Lost tracks:__ If a track hasn't been associated with a detection for a certain number of frames, SORT considers it lost and removes it.

    3.4  __Output:__ SORT provides a list of tracks, each containing a unique ID, bounding box, predicted motion, and other relevant information.


## Combined Workflow
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
1.  Each frame is processed by YOLOv7 for object detection.
  
2.  SORT receives the detections and associates them with existing tracks or creates new ones.
  
3.  The final output combines YOLOv7's class and confidence information with SORT's track IDs and motion data, giving you a clear picture of objects and their movements across frames.

## Output
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
![image](https://github.com/Mahi4052/Multiple-Object-Detection-Tracking-Counting/assets/95848665/71c40565-80e1-46d9-9034-2bf9ef3c31c5)


## Benefits of using YOLOv7 and SORT together
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
1.  __Accurate detections:__ YOLOv7's superior detection accuracy provides reliable input for SORT.
  
2.  __Robust tracking:__ SORT's algorithm handles occlusions, missed detections, and changes in appearance effectively.
  
3.  __Real-time performance:__ Both YOLOv7 and SORT are optimized for real-time applications, making them suitable for video surveillance, robot navigation, and other time-sensitive tasks.

# For More Information
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Please check out the main file of project [detect_and_track](https://github.com/Mahi4052/Multiple-Object-Detection-Tracking-Counting/blob/main/detect_or_track.py)

Video process data used [street.mp4](https://github.com/Mahi4052/Multiple-Object-Detection-Tracking-Counting/blob/main/street.mp4)


