# Two-View-Depth-Estimation
## Problem Statement
● Estimating the 3D coordinates of objects from two images captured
from different viewpoints

● challenging task due to the differences in the orientations,
positions, and scales of the two images, and the presence of noise and
outliers

● Many practical applications in robotics, augmented reality, 3D
modeling

## Dataset Description and Demonstration
● We are using Middlebury Dataset for Two-view Depth Estimation

● One of the most popular and widely-used benchmarks

● Dataset consists of pairs of images of the same scene taken from two different
viewpoints

● Contains intrinsic parameter of the camera, baseline, x-difference of principal points
and ground truth

● Includes multiple resolutions and color spaces, such as gray, RGB, and infrared

## Dataset Description and Demonstration
● Import data online and convert it into the matrix

● Stored that matrix on the drive using Pickle

● There are 23 pairs of images and camera intrinsic parameters
![Screenshot 2023-08-02 at 8 07 12 PM](https://github.com/rohit-vishwas/Two-View-Depth-Estimation/assets/57809391/5be90787-f9a8-405c-af8f-2a4310f1ec53)
![Screenshot 2023-08-02 at 8 07 50 PM](https://github.com/rohit-vishwas/Two-View-Depth-Estimation/assets/57809391/30f57868-8ac9-4351-8688-df29beea00c7)

## Methodology
![Screenshot 2023-08-02 at 8 09 00 PM](https://github.com/rohit-vishwas/Two-View-Depth-Estimation/assets/57809391/07efd090-912c-4dce-a24e-c4f812e1e513)


Calculated Fundamental matrix: used SVD to find the F
Used RANSAC (Random Sample Consensus) to find the best Fundamental matrix.
Calculated Essential matrix using Fundamental matrix find the epipolar constraint first using F
then calculated the E, using epipolar constraint
Computed Camera pose (R and t) using Essential matrix. using equation [tx]R = E

● Mapped 2D points into 3D points with the help of TriangulatePoints
● Made a kernel of window size 5 and iterate over all points of 3D point
● Compute Disparity map
● Compute Depth map
![Screenshot 2023-08-02 at 8 11 38 PM](https://github.com/rohit-vishwas/Two-View-Depth-Estimation/assets/57809391/42d33e5c-95bb-4eb3-b7bb-c46876091592)
![Screenshot 2023-08-02 at 8 12 11 PM](https://github.com/rohit-vishwas/Two-View-Depth-Estimation/assets/57809391/c355092c-bc7e-4ffe-9e76-e08d0acdfb80)
![Screenshot 2023-08-02 at 8 13 28 PM](https://github.com/rohit-vishwas/Two-View-Depth-Estimation/assets/57809391/6189dd28-3a4e-4ae4-a297-bbd31bbb328e)
![Screenshot 2023-08-02 at 8 14 03 PM](https://github.com/rohit-vishwas/Two-View-Depth-Estimation/assets/57809391/accf716c-ca4d-4647-82c9-bb43fd66bb0a)


