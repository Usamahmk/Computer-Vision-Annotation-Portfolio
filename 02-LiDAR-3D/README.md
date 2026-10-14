# LiDAR 3D Object Tracking & Point Cloud Annotation

## Project Overview

This project demonstrates my practical experience in 3D object tracking and LiDAR point-cloud annotation using CVAT.

The annotation task uses sequential point-cloud data to track selected objects across five frames. I used 3D cuboids, object tracking, and interpolation to maintain object identities and spatial consistency across the sequence.

## Project Details

| Category | Description |
|---|---|
| Annotation Tool | CVAT |
| Data Type | Sequential LiDAR Point Clouds |
| Annotation Type | 3D Cuboid Tracking |
| Annotated Frames | 5 |
| Tracking Method | Multi-frame object tracking |
| Interpolation | Used |
| Object Classes | To be confirmed |
| Dataset Name | To be confirmed |


## Video Demonstration

This video demonstrates my LiDAR 3D point-cloud annotation workflow in CVAT, including 3D cuboid annotation, object tracking, and interpolation across sequential frames.

[![Watch My LiDAR 3D Annotation Demo](https://img.youtube.com/vi/xC4R7dE_D-4/hqdefault.jpg)](https://youtu.be/xC4R7dE_D-4)

**[Watch the full demonstration on YouTube](https://youtu.be/xC4R7dE_D-4)**
  

## Annotation Evidence

### 1. 3D Object Tracking — Frame 0

![3D object tracking overview](screenshots/01-3d-object-tracking.png)

*Overview of the annotated LiDAR point cloud with multiple 3D cuboids and orthographic views.*

### 2. Cuboid Alignment and Orientation

![3D cuboid alignment](screenshots/02-cuboid-alignment.png)

*Selected 3D cuboid examined from perspective, top, side, and front views to assess spatial alignment.*

### 3. Tracking and Keyframe Workflow — Frame 10

![Tracking and keyframe workflow](screenshots/03-interpolation-keyframes.png)

*CVAT cuboid-track panel displaying object classes, tracking controls, and pedestrian cuboid dimensions at frame 10.*

### 4. Sequential Object Tracking — Frame 20

![Sequential frame tracking](screenshots/04-sequential-frame-tracking.png)

*Later LiDAR frame showing tracked objects, including pedestrian track ID 12, for temporal consistency review.*

### 5. Quality Assurance Inspection

![LiDAR 3D QA review](screenshots/05-qa-review.png)

*Inspection of a selected pedestrian cuboid and its dimensions using the available point-cloud views.*
## Annotation Workflow

1. Import the sequential LiDAR point-cloud dataset into CVAT.
2. Inspect the point-cloud scene and identify target objects.
3. Create 3D cuboids around selected objects.
4. Adjust cuboid position, dimensions, and orientation.
5. Track objects across the five-frame sequence.
6. Use interpolation to support annotation between frames.
7. Review object identities and cuboid alignment.
8. Correct identified annotation issues.

## Quality Assurance

The QA process focuses on:

- Accurate 3D cuboid placement
- Correct object classification
- Cuboid dimensions and orientation
- Consistent tracking identities
- Interpolation accuracy
- Annotation consistency across frames

**QA findings:** To be documented from the completed review.

## Supporting Documentation

- [Annotation Guidelines](annotation-guidelines.md)
- [Difficult Cases](difficult-cases.md)
- [Tracking QA Report](tracking-qa-report.md)

## Portfolio

[Back to Computer Vision Annotation Portfolio](../README.md)
