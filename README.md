# Aruco_Marker
Aruco market python code for real-time, but centimeter level precision.


Folder Structure:
.
 calib_data/                  # Folder to store the calibration data (MultiMatrix.npz)
 images/                      # Folder where captured checkerboard images are saved
 image_capture.py             # Script to capture checkerboard images and save calibration data
 calib.py                     # Script to calibrate the image and generate the 'MultiMatrix.npz' 
 aruco_pose_estimation.py     # Script to read ArUco markers and estimate pose



Step 1: Capture Checkerboard Images

    Ensure that the images/ directory exists in your project folder. If not, it will be created automatically.
    Use the image_capture.py script to open the webcam and capture multiple images of a physical checkerboard.
    For each image, the script detects the checkerboard pattern and saves the image if the pattern is successfully detected. Press the 's' key to save an image and 'q' to quit.
    After capturing a sufficient number of images, start the calib.py

Step 2: Camera Calibration

Once you have enough images (typically 10-20), the calib.py will:

    Load the captured checkerboard images.
    Detect the checkerboard corners in each image.
    Perform camera calibration using OpenCV's cv2.calibrateCamera() method.
    Save the calibration data (camera matrix, distortion coefficients, rotation vectors, and translation vectors) into the MultiMatrix.npz file located in the calib_data/ folder.

Step 3: Run the aruco_pose_estimation.py

## The code can be modified into giving the feature that you want, distance / only the vertex or if you want x,y cords. The code can be easily manipulated

