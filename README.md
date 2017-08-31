## Video Pipeline
### Complete Process Involves
*  **Calibrate** - Use Camera Calibrate Function to get Distortion Matrix
*   **Undistort** -  Use Computed Distortion Matrix to correct for Distortion
<img src="CameraCalibrationProcess.png">
*   **Warp** - Use Warping Function to get Bird's eye view 
<img src="Image_Warp_Process.png">
*   **Threshold** - Use a combination of static , dynamic thresholding with morph transformations & colorspaces to get thresholded image
<img src="Threshold_Process.png">

*   **Extract Pixel Information** - Use Quantity based thresholding to and extract non-zero pixels
*   **Validate and Fit** - Use Curvature and LaneWidth Sanity mechanisms to check the validity of the two fits obtained for a given frame and decide on whether to use the current fit or use an extrapolated average of the previous fits 
<img src="Validation_DecisionTree.png">
*   **Project Fit on to Image ** - Convert the x, y plane points and fit to image plane points and draw polygon on the image.
*   **Unwarp** - Use Inverse Perspective Transform to unwarp the image. 
<img src="Unwarp_process.png">

*   **Output** - Return the processed frame . 
<img src="Complete_process.png">

### Example Images from Each of the video 
#### Harder Challenge
<img src="Harder_Challenge_Video_Pipeline.png">
#### Challenge Video 
<img src="Challenge_ Video_pipeline.png">
#### Project Video
<img src="Project_Video_Pipeline.png">

## Camera Calibration 
* Get Chessboard Corners from Standard Images
* Calibrate Camera using differences in distances between expected and actual results
* Use Calibration data to Undistort Camera Images
<img src ="Camera_Calibration.png">
* Example of how Chessboard Corners are obtained before Calibration to Undstort and use it to have a Bird's Eye Perspective
<img src="Camera_calibration_Example.png">

## Warping & Birds Eye View Generation
* Use Interactive Python to plot and understand what is the best set of source and destination points for each/ all the three videos of interest. After several days of experimentation we have finally arived at these numbers
* Use Get Perspective Transform for Matrix calculation that can be used to Warp The Image to Bird's eye view and Unwarp them back to the front view
<img src="Warp_Image_Final.png">

## Image Thresholding 
<img src= "Image_Thresholding_Final.png">
### Morphological Channel :
* Use HLS S- Channel and Gray Channel to create Morphological Channel
* Threshold the Morph Channel to get the most dominant features 
* Determine Levels of Thresholds using Mean and Standard Deviations 

### Environment Mask :
* Use B-Channel from the LAB Colorspace to choose Yellow and Shades of Yellow 
* Use HLS Channel to filter out everything not in range of threshold. "
<img src= "Detailed_ThreshProcess.png">
