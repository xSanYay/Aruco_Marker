# Aruco_Marker

## Aruco Marker Python Code for Real-Time, Centimeter-Level Precision

This project uses ArUco markers for real-time pose estimation with centimeter-level precision.

---

## Folder Structure:

- `calib_data/`                  # Folder to store the calibration data (`MultiMatrix.npz`)
- `images/`                       # Folder where captured checkerboard images are saved
- `image_capture.py`              # Script to capture checkerboard images and save calibration data
- `calib.py`                      # Script to calibrate the image and generate the `MultiMatrix.npz`
- `aruco_pose_estimation.py`      # Script to read ArUco markers and estimate pose

---

## Step 1: Capture Checkerboard Images

1. Ensure the `images/` directory exists in your project folder. If not, it will be created automatically.
2. Use the `image_capture.py` script to open the webcam and capture multiple images of a physical checkerboard.
3. The script detects the checkerboard pattern and saves the image if the pattern is successfully detected.
   - Press the 's' key to save an image.
   - Press 'q' to quit the script.
4. Once you’ve captured a sufficient number of images, proceed to **Step 2**.

---

## Step 2: Camera Calibration

1. Once you have enough images (typically 10-20), run `calib.py` to perform the calibration.
2. The script will:
   - Load the captured checkerboard images.
   - Detect the checkerboard corners in each image.
   - Perform camera calibration using OpenCV’s `cv2.calibrateCamera()` method.
3. The calibration data (camera matrix, distortion coefficients, rotation vectors, and translation vectors) will be saved in the `MultiMatrix.npz` file inside the `calib_data/` folder.

---

## Step 3: Run `aruco_pose_estimation.py`

1. After calibration, run the `aruco_pose_estimation.py` script to read ArUco markers and estimate pose.
2. **Customization**: The code can be modified to provide specific features such as:
   - Distance estimation
   - Only displaying the vertices of the markers
   - Getting the x, y coordinates of the markers
   
   The code is designed to be easily manipulated based on your specific requirements.

---

## Notes

- Ensure that you have the necessary dependencies installed, such as OpenCV and NumPy.
- The code uses the camera calibration data stored in `MultiMatrix.npz` to accurately estimate the pose of ArUco markers.
