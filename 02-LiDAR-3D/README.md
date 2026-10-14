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

My demonstration video showcases the 3D point-cloud annotation workflow, including cuboid placement, object tracking, interpolation, and frame review.

**Video link:** To be added.

## Annotation Evidence

### 1. 3D Object Tracking

Screenshot to be added.

This screenshot will demonstrate 3D cuboid tracking within the CVAT point-cloud interface.

### 2. Cuboid Alignment and Orientation

Screenshot to be added.

This screenshot will demonstrate how 3D cuboids are positioned and aligned with LiDAR points.

### 3. Sequential Frame Review

Screenshot to be added.

This screenshot will demonstrate annotation consistency across the selected point-cloud frames.

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
