## Advanced Lane Finding
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)
![Lanes Image](./examples/example_output.jpg)

In this project, goal is to write a software pipeline to identify the lane boundaries in a video

## Files
1. CarND-Advanced-Lane-Lines Assignment.ipynb - Jupyter notebook
2. test_videos_output/project_video_Solution.mp4 - Output Video File
3. Intermediate Images - Both in Jupyter notebook and test_images_undistort folder
4. The images for camera calibration are stored in the folder called `camera_cal`
5. The images in `test_images` are for testing your pipeline on single frames. 

## Steps


The steps of this project are the following:

* Computed the camera calibration matrix and distortion coefficients given a set of chessboard images in camera_cal folder 
* The distortion correction found was tested on calibration2.jpg
* The undistored image was passed through sobel filters to detect the lane edges
* To compensate for brightness changes, thresholding is done on S channel after converting the image to HLS format
* Both the sobel filter and S channel output was combined to identify lanes in brightness and color gradient changes
* For identifying the lane curvature, images need to be rotated to a bird eye view. For this, four coordinates are chosen by eye balling 
* In the warped image containing the two lanes, histogram was created to created to find the base of both the lanes
* With the base identified, non zero pixels were identified with sliding windows. With all the non pixels found, quadritic line was fit to get both the lanes
* The detected lane boundaries were warped back onto the original image.
* Output visual display of the lane boundaries and numerical estimation of lane curvature and vehicle position.

## Scope of improvement
* Maintain a dictionary which can be used to extrapolate the lanes using historical data
* Improving lane detection algorithm to work better on sharp turns (instead of adjusting coordinates for warping the lanes correctly)
* Work on extreme brightness changes (coming out of the tunnel)

