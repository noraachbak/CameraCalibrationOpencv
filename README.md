# CameraCalibrationOpencv

Camera Calibration Using OpenCV

Example output YAML file: contains the coefficents and the camera matrix

camera_matrix:
- [843.30808736, 0.0, 299.83093674]
- [0.0, 796.82807368, 311.97096496]
- [0.0, 0.0, 1.0]
dist_coefs:
- [-0.74823162, 1.20896823985868346, -0.0003239082442461539, -0.0019027617884934114,
  -4.0668551319250156]
rms: 0.1414231691868478

Example usage ( the input data is present in the ./example_input):

$ mkdir out
$ ./calibrate.py example_input/chessboard.avi calibration.yaml --debug-dir out

##########################Removing Radial Distortion######################################
You can test the found radial distortion coefficients by removing distortion from an image and checking if 
straight lines are really straight.
./undistort.py calibration.yaml 'example_input/*.png' out/
