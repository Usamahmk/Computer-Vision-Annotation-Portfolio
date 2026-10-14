# LiDAR 3D Annotation — Difficult Cases and Resolution Guidelines

## 1. Overview

This document describes challenging situations relevant to LiDAR 3D cuboid annotation and object tracking using CVAT.

The project uses selected sequential point-cloud samples from the KITTI dataset, with 3D cuboid annotations, object tracking, and interpolation using variable keyframe intervals.

The cases below explain the review procedures and recommended resolutions. They are not presented as verified errors or corrections unless supported by the project evidence.

## 2. Case 1 — Sparse LiDAR Point Clouds

**Challenge:** Distant objects may contain only a small number of LiDAR points, making their dimensions and orientation difficult to determine.

**Resolution Guidelines:**

1. Inspect the object from perspective, top, side, and front views.
2. Identify the points most likely to belong to the target object.
3. Adjust cuboid dimensions conservatively.
4. Compare the object with adjacent frames when possible.
5. Avoid expanding the cuboid beyond what the evidence reasonably supports.

**Quality Objective:** Minimize inaccurate cuboid sizing and unsupported assumptions about object boundaries.

## 3. Case 2 — Partial Occlusion

**Challenge:** A vehicle or pedestrian may be partially hidden by another object, leaving an incomplete point-cloud representation.

**Resolution Guidelines:**

1. Review the visible LiDAR points.
2. Examine earlier and later frames for additional context.
3. Maintain the existing track ID when the object's identity remains supported.
4. Avoid estimating hidden geometry without sufficient evidence.
5. Follow the project's annotation policy when the object's position becomes uncertain.

**Quality Objective:** Preserve tracking continuity without introducing unsupported annotations.

## 4. Case 3 — Cuboid Misalignment

**Challenge:** A 3D cuboid may appear correctly positioned from one viewing angle but be inaccurate from another.

**Resolution Guidelines:**

1. Inspect the cuboid in perspective view.
2. Use top view to check position and heading.
3. Use side and front views to assess height and dimensions.
4. Adjust the cuboid when the available points indicate misalignment.
5. Recheck all views after adjustment.

**Quality Objective:** Improve cuboid placement and orientation consistency.

## 5. Case 4 — Interpolation Drift

**Challenge:** Interpolated cuboids may not follow an object's actual movement accurately, especially when its motion or orientation changes.

**Resolution Guidelines:**

1. Review frames between manually defined keyframes.
2. Compare interpolated cuboids with the available point-cloud evidence.
3. Identify frames where cuboid position, size, or orientation appears inconsistent.
4. Add or adjust keyframes when necessary.
5. Recheck the interpolated sequence.

**Quality Objective:** Maintain accurate 3D tracking between keyframes.

## 6. Case 5 — Object Identity Confusion

**Challenge:** Nearby cars or pedestrians may appear similar, increasing the risk of assigning the wrong track ID.

**Resolution Guidelines:**

1. Examine the object's location in preceding and following frames.
2. Compare its movement and spatial relationship to nearby objects.
3. Preserve the existing track ID when continuity is supported.
4. Avoid assigning a new ID solely because an object changes position.
5. Review uncertain transitions before finalizing the track.

**Quality Objective:** Reduce identity switches and fragmented object tracks.

## 7. Case 6 — Variable Keyframe Intervals

**Challenge:** Fixed keyframe spacing may be unsuitable when object movement varies across a sequence.

**Resolution Guidelines:**

1. Select keyframes based on changes in object position and orientation.
2. Use shorter intervals when motion becomes difficult to interpolate.
3. Use longer intervals when movement is sufficiently predictable.
4. Inspect the resulting interpolation.
5. Refine keyframe placement when tracking accuracy requires it.

**Quality Objective:** Balance annotation efficiency with temporal consistency.

## 8. Quality Assurance Checklist

- [x] Inspect difficult cuboids from multiple viewing angles.
- [x] Check cuboid dimensions and orientation.
- [x] Review interpolated frames for drift.
- [x] Verify object identity continuity.
- [x] Examine sparse or partially occluded objects.
- [x] Correct confirmed annotation issues.
- [x] Record unresolved ambiguities for further review.

## 9. Project Evidence

The project README includes screenshots from the sequential KITTI LiDAR tracking task, showing cuboid annotations and inspection across multiple frames.

A separate five-frame video demonstrates the CVAT LiDAR annotation workflow.

**Video:** [https://youtu.be/xC4R7dE_D-4](https://youtu.be/xC4R7dE_D-4)

**Dataset:** [https://www.cvlibs.net/datasets/kitti/](https://www.cvlibs.net/datasets/kitti/)
