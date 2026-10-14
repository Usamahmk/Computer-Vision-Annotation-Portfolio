# Quality Assurance Report
## CVAT 2D Object Tracking and Bounding Box Annotation

### 1. Project Overview

This report documents the quality assurance process for a targeted 2D video object-tracking exercise completed using CVAT.

| Project Detail | Description |
|---|---|
| Annotation Tool | CVAT |
| Annotation Type | 2D Rectangle Tracking |
| Annotated Frame Range | 0–50 |
| Total Frames Annotated | 51 |
| Number of Tracked Objects | 4 |
| Object Classes | Motorcycle (2), Person (2) |
| Keyframe Interval | Every 10 frames |
| Keyframes | 0, 10, 20, 30, 40, 50 |
| Annotation Method | Manual keyframes with interpolation |
| QA Method | Individual frame-by-frame review |

**Annotation Scope:** This exercise focuses on four selected objects rather than every visible road user.

### 2. Annotation Methodology

The video was annotated from frame 0 through frame 50 using CVAT's rectangle tracking functionality.

Bounding boxes were manually positioned at regular 10-frame intervals, with keyframes at frames 0, 10, 20, 30, 40, and 50.

CVAT interpolation was used to estimate object positions between keyframes. Intermediate frames were then reviewed individually to verify that the bounding boxes followed the correct objects.

Each of the four selected targets was assigned a tracking identity to maintain consistency throughout the annotated sequence.

### 3. Quality Assurance Results

| QA Metric | Result |
|---|---|
| Frames individually reviewed | 51 |
| Tracked objects | 4 |
| Tracking ID switches | 0 |
| Bounding-box placement errors | 0 reported |
| Interpolation drift issues detected | 2 |
| Interpolation drift issues corrected | 2 |
| Unresolved interpolation drift issues | 0 reported |
| Keyframe interval | 10 frames |

### 4. Issues Identified and Corrective Actions

**Issue: Interpolation Drift**

During frame-by-frame QA, two instances of interpolation drift were identified.

**Corrective Action:**

The affected bounding boxes were adjusted in CVAT to better align with the target objects. The relevant frames were reviewed after correction.

**Outcome:**

Both identified interpolation drift issues were corrected. No tracking ID switches or other bounding-box placement errors were reported during the review.

### 5. Quality Assurance Checklist

- [x] Verify the four selected target objects
- [x] Check motorcycle and person classifications
- [x] Review frames 0–50 individually
- [x] Check keyframes at 10-frame intervals
- [x] Review bounding-box alignment
- [x] Check for tracking ID switches
- [x] Identify interpolation drift
- [x] Correct two interpolation drift issues
- [x] Review corrected annotations

### 6. Evidence

**Object Tracking Screenshot**

![Four selected objects tracked in CVAT](screenshots/01-object-tracking.png)

**Bounding Box Annotation Screenshot**

![Separate car bounding-box annotation exercise](screenshots/02-bounding-box-accuracy.png)

**Frame 40 Tracking Screenshot**

![Selected tracked objects at frame 40](screenshots/03-keyframe-review.png)

**Video Demonstration**

[Watch CVAT 2D Object Tracking Demonstration](https://youtu.be/PD7wA10ZvYc)

### 7. QA Conclusion

The targeted annotation exercise covered 51 frames, from frame 0 through frame 50, with four tracked objects and keyframes at 10-frame intervals.

Individual frame-by-frame QA identified two interpolation drift issues, both of which were corrected. No tracking ID switches or additional bounding-box placement errors were reported.

**Final QA Status: Completed — all identified issues corrected.**

These findings apply only to the four selected tracking targets within the annotated frame range.
