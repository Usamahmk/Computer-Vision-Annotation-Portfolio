# LiDAR 3D Annotation Guidelines

## 1. Project Overview

This document describes the annotation workflow and quality-control guidelines for a LiDAR 3D object tracking project completed using CVAT (Computer Vision Annotation Tool).

The project uses a selected subset of sequential LiDAR point-cloud samples from the **KITTI Vision Benchmark Suite**.

The annotation work focuses on 3D cuboid placement, object classification, tracking consistency, and keyframe-based interpolation.

## 2. Dataset Preparation

- **Dataset:** KITTI Vision Benchmark Suite
- **Annotation Platform:** CVAT
- **Data Type:** Sequential LiDAR point clouds
- **Annotation Geometry:** 3D cuboids
- **Confirmed Object Classes:** Car and Pedestrian

### Preparation Procedure

1. Obtain LiDAR point-cloud samples from the KITTI dataset.
2. Select a subset of samples for the annotation project.
3. Upload the selected point-cloud samples into CVAT.
4. Configure the appropriate object labels.
5. Begin 3D cuboid annotation and tracking.

## 3. 3D Cuboid Annotation Guidelines

Each 3D cuboid should represent the visible spatial extent of its target object as accurately as the available point-cloud evidence allows.

### Cuboid Placement

- Position the cuboid around the target object's point-cloud representation.
- Adjust its length, width, and height to fit the object.
- Check the cuboid's position using perspective, top, side, and front views.
- Avoid unnecessarily large or poorly aligned cuboids.
- Review sparse or partially visible objects carefully.

### Cuboid Orientation

- Align the cuboid's heading with the object's estimated orientation.
- Use the available point-cloud geometry and viewing angles to assess alignment.
- Avoid changing orientation without sufficient visual evidence.

## 4. Object Classification

Assign labels according to the configured annotation taxonomy.

Examples of object classes shown in this project include:

- **Car:** Passenger vehicles represented in the point cloud.
- **Pedestrian:** People represented by LiDAR points.

If an object's class is uncertain, review the available evidence before assigning a label. Do not guess solely from cuboid size.

## 5. Multi-Frame Object Tracking

Tracking maintains an object's identity across sequential point-cloud frames.

### Tracking Rules

1. Assign a consistent track ID to each tracked object.
2. Maintain the same ID while the object remains identifiable across frames.
3. Adjust the cuboid as the object's position or orientation changes.
4. Review adjacent frames when object identity is uncertain.
5. Avoid creating unnecessary new tracks for the same object.

## 6. Keyframe-Based Interpolation

The tracking workflow uses **variable keyframe intervals** rather than a fixed interval.

### Interpolation Procedure

1. Create a 3D cuboid track for the target object.
2. Set a keyframe at a suitable point in the sequence.
3. Move to another frame and adjust the cuboid as needed.
4. Allow CVAT to interpolate the cuboid between keyframes.
5. Inspect interpolated frames for positioning, sizing, and orientation errors.
6. Add or adjust keyframes where interpolation does not adequately represent the object's movement.

Keyframe spacing should reflect changes in object motion and the quality of the available point-cloud evidence.

## 7. Difficult Annotation Cases

### Sparse Point Clouds

Use the available LiDAR points and multiple viewing angles to estimate object boundaries conservatively.

### Partial Occlusion

Keep the object identity consistent when supported by the sequence. Avoid unsupported assumptions about hidden geometry.

### Object Movement

Inspect interpolated cuboids when objects change position, direction, or apparent orientation.

### Similar Nearby Objects

Use spatial continuity and frame-to-frame evidence to reduce the risk of track ID switches.

## 8. Quality Assurance Checklist

- [x] Cuboids are positioned around their intended objects.
- [x] Cuboid dimensions are reasonable for the visible point-cloud evidence.
- [x] Object labels follow the configured taxonomy.
- [x] Cuboid orientation is consistent with available evidence.
- [x] Track IDs remain consistent across identifiable frames.
- [x] Interpolated cuboids are inspected for drift.
- [x] Ambiguous objects are reviewed rather than guessed.
- [x] Annotation results are inspected from multiple viewing angles.

## 9. Demonstration and Evidence

The portfolio contains a separate five-frame video demonstration showing the 3D annotation workflow.

Additional screenshots document a larger sequential LiDAR tracking task, including cuboid tracks, object properties, and frame-based inspection.

**Video Demonstration:** [https://youtu.be/xC4R7dE_D-4](https://youtu.be/xC4R7dE_D-4)

**Dataset Reference:** [https://www.cvlibs.net/datasets/kitti/](https://www.cvlibs.net/datasets/kitti/)
