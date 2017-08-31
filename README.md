## Camera Calibration with OpenCV

The IPython notebook in this repository contains code to calculate the camera matrix and distortion coefficients using the images in the "calibration_wide" folder.
## Video Pipeline
### Complete Process Involves
* **Calibrate** - Use Camera Calibrate Function to get Distortion Matrix
* **Undistort** -  Use Computed Distortion Matrix to correct for Distortion
<img src="CameraCalibrationProcess.png">
* **Warp** - Use Warping Function to get Bird's eye view 
<img src="Image_Warp_Process.png">
* **Threshold** - Use a combination of static , dynamic thresholding with morph transformations & colorspaces to get thresholded image
<img src="Threshold_Process.png">

* **Extract Pixel Information** - Use Quantity based thresholding to and extract non-zero pixels
* **Validate and Fit** - Use Curvature and LaneWidth Sanity mechanisms to check the validity of the two fits obtained for a given frame and decide on whether to use the current fit or use an extrapolated average of the previous fits 
<img src="Validation_DecisionTree.png">
* **Project Fit on to Image ** - Convert the x, y plane points and fit to image plane points and draw polygon on the image.
* **Unwarp** - Use Inverse Perspective Transform to unwarp the image. 
<img src="Unwarp_process.png">

* **Output** - Return the processed frame . 
<img src="Complete_process.png">

### Example Images from Each of the video 
#### Harder Challenge
<img src="Harder_Challenge_Video_Pipeline.png">
#### Challenge Video 
<img src="Challenge_ Video_pipeline.png">
#### Project Video
<img src="Project_Video_Pipeline.png">
