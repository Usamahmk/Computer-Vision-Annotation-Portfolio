# LiDAR 3D Object Tracking — Quality Assurance Report

## 1. Executive Summary

This report documents the quality assurance (QA) process performed on a LiDAR 3D object annotation and tracking project using **CVAT (Computer Vision Annotation Tool)**.

The project used a selected subset of sequential point-cloud samples from the **KITTI Vision Benchmark Suite**.

The annotation workflow involved:

- 3D cuboid placement and alignment
- Object classification
- Multi-frame object tracking
- Keyframe-based interpolation using variable intervals
- Manual review and correction of annotation errors
- Tracking identity consistency checks

**QA Outcome:** All frames in the larger sequential tracking task were reviewed. No track ID switches were observed during review. Cuboid alignment and interpolation issues were identified and corrected.

The project also includes a separate five-frame video demonstration showing the CVAT LiDAR annotation workflow. The video sample is not the basis for the larger tracking task's QA results.

---

## 2. Project Information

| Field | Description |
|---|---|
| Project | LiDAR 3D Object Annotation and Tracking |
| Dataset Source | KITTI Vision Benchmark Suite |
| Dataset Preparation | Selected subset of sequential LiDAR samples |
| Annotation Platform | CVAT |
| Data Type | 3D LiDAR point clouds |
| Annotation Geometry | 3D cuboids |
| Confirmed Object Classes | Car, Pedestrian |
| Annotation Method | Manual cuboid annotation with keyframe-based interpolation |
| Keyframe Spacing | Variable intervals |
| QA Method | Manual visual inspection |
| QA Coverage | All frames in the larger tracking sequence |
| Video Demonstration | Separate five-frame sample |

## 3. Quality Assurance Objectives

The QA process focused on the following objectives:

1. **Cuboid Accuracy:** Check whether 3D cuboids fit their intended objects.
2. **Spatial Alignment:** Review cuboid position, dimensions, and orientation.
3. **Tracking Consistency:** Verify that object identities remain consistent across sequential frames.
4. **Interpolation Quality:** Identify and correct inaccuracies between manually annotated keyframes.
5. **Label Consistency:** Check object classifications against the configured taxonomy.
6. **Temporal Continuity:** Review how tracked cuboids change across the sequence.

## 4. QA Review Methodology

### 4.1 Frame-by-Frame Review

All frames in the larger sequential LiDAR tracking task were reviewed.

The review focused on cuboid positioning, object identity continuity, and the quality of interpolated annotations.

### 4.2 Multi-View Cuboid Inspection

CVAT's available point-cloud views were used to examine 3D annotations:

- **Perspective view:** General cuboid positioning and spatial context.
- **Top view:** Object position, width, length, and heading.
- **Side view:** Cuboid height, length, and vertical alignment.
- **Front view:** Cuboid width, height, and lateral alignment.

These views supported the identification and correction of cuboid placement issues.

### 4.3 Tracking Identity Review

Object tracks were examined across sequential frames to assess whether their IDs remained associated with the same physical objects.

Particular attention was given to maintaining identity continuity as objects changed position.

**Result:** No track ID switches were observed during the review.

### 4.4 Interpolation Review

The annotation task used variable keyframe intervals rather than a fixed spacing.

Interpolated cuboids were checked against the available LiDAR points to assess whether their positions and orientations remained appropriate between keyframes.

Where issues were identified, corrections were made to improve the annotations.

## 5. QA Findings and Results

| Quality Check | Recorded Result | Status |
|---|---|---|
| Frame review coverage | All frames in the larger sequence reviewed | Completed |
| Track ID consistency | No ID switches observed | Passed visual review |
| Cuboid alignment | Issues identified and corrected | Corrected |
| Interpolation quality | Issues identified and corrected | Corrected |
| Keyframe spacing | Variable intervals used | Documented |
| Multi-view inspection | Cuboids reviewed using available views | Completed |
| Exact number of corrections | Not recorded | Not quantified |
| Numerical 3D IoU accuracy | Not measured | Not reported |

**Important:** These findings reflect manual QA observations. They do not represent independently benchmarked 3D detection accuracy or automated tracking evaluation.

## 6. Issues Identified and Corrective Actions

### 6.1 Cuboid Alignment Issues

**Issue:** Some 3D cuboid annotations required adjustments to improve their alignment with the LiDAR point-cloud evidence.

**Corrective Action:**

1. Inspected the affected cuboids using multiple viewing angles.
2. Reviewed cuboid position, dimensions, and orientation.
3. Adjusted the annotations where necessary.
4. Rechecked the corrected cuboids against the available point-cloud evidence.

**Outcome:** Identified alignment issues were corrected during the QA process.

### 6.2 Interpolation Issues

**Issue:** Some interpolated annotations required corrections to better represent objects between keyframes.

**Corrective Action:**

1. Reviewed the affected intermediate frames.
2. Compared interpolated cuboids with the visible LiDAR points.
3. Adjusted annotations and keyframes where needed.
4. Rechecked the resulting tracking sequence.

**Outcome:** Identified interpolation issues were corrected during review.

### 6.3 Object Identity Consistency

**Risk:** Object identity confusion can occur when multiple objects are tracked across sequential frames.

**Review Approach:**

1. Inspected tracked objects across the sequence.
2. Compared object locations and movement between frames.
3. Checked whether track IDs remained associated with their intended objects.

**Outcome:** No track ID switches were observed.

## 7. QA Metrics and Reporting Limitations

This project used manual visual quality assurance rather than automated benchmark evaluation.

### Confirmed Results

- All frames in the larger sequential tracking task were reviewed.
- No track ID switches were observed.
- Cuboid alignment corrections were performed.
- Interpolation corrections were performed.
- Variable keyframe intervals were used.

### Metrics Not Quantified

The following numerical metrics were not recorded and are therefore not claimed:

- Total number of cuboid corrections
- Total number of interpolation corrections
- Mean 3D Intersection over Union (IoU)
- Automated tracking accuracy scores
- Inter-annotator agreement
- Benchmark precision or recall

This distinction ensures that the portfolio presents verifiable work and avoids unsupported performance claims.

## 8. Final QA Checklist

- [x] Review all frames in the larger tracking sequence.
- [x] Inspect cuboid placement and alignment.
- [x] Review cuboid dimensions and orientation.
- [x] Check object tracking identity consistency.
- [x] Inspect interpolated annotations.
- [x] Correct identified cuboid alignment issues.
- [x] Correct identified interpolation issues.
- [x] Examine annotations using multiple viewing angles.
- [x] Document the observed QA results.

## 9. Portfolio Evidence

### Screenshot Evidence — Larger KITTI Tracking Task

The project README contains five screenshots showing 3D cuboid annotations, tracked objects, object properties, and sequential frame inspection.

Screenshots include frames 0, 10, and 20 from the larger task.

These screenshots provide visual examples of the annotation environment and tracking workflow. They do not independently establish every QA result recorded in this report.

### Video Demonstration — Separate Five-Frame Sample

A separate video demonstrates LiDAR 3D annotation and bounding-box placement in CVAT using a five-frame sample.

**Watch the demonstration:** https://youtu.be/xC4R7dE_D-4

The video demonstrates annotation techniques and is distinct from the larger task documented in the screenshot evidence and QA findings.

## 10. Conclusion

The LiDAR 3D tracking task was completed with a manual quality assurance process covering all frames in the larger sequential dataset subset.

The review identified cuboid alignment and interpolation issues, which were corrected. No track ID switches were observed.

This project demonstrates practical experience in LiDAR 3D cuboid annotation, multi-frame object tracking, keyframe-based interpolation, and manual annotation quality assurance using CVAT.

---

**Dataset Reference:** [KITTI Vision Benchmark Suite](https://www.cvlibs.net/datasets/kitti/)

**Annotation Platform:** CVAT

**Related Documents:**

- [Project README](README.md)
- [Annotation Guidelines](annotation-guidelines.md)
- [Difficult Cases and Resolution Guidelines](difficult-cases.md)
