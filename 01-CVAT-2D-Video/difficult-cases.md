# Difficult Cases and Corrective Actions
## CVAT 2D Object Tracking

### 1. Project Context

This document describes annotation challenges and quality assurance decisions encountered during a targeted 2D object-tracking exercise using CVAT.

**Project scope:**
- Annotated frames: 0–50 (51 frames)
- Selected tracking targets: 2 motorcycles and 2 people
- Keyframes: 0, 10, 20, 30, 40, 50
- Annotation method: Rectangle tracks with interpolation
- QA method: Individual frame-by-frame review

Only the four selected objects were included in the tracking scope.

### 2. Case Study 1 — Interpolation Drift

**Problem**

During frame-by-frame review, two interpolation drift issues were identified.

Interpolation drift occurs when an automatically interpolated bounding box does not remain accurately aligned with the target object's position or size between manually defined keyframes.

**Detection**

The issues were identified during manual inspection of the annotated frames.

**Corrective Action**

The affected annotations were corrected in CVAT, and the corrected tracking results were reviewed.

**Outcome**

- Interpolation drift issues detected: 2
- Interpolation drift issues corrected: 2
- Unresolved reported interpolation issues: 0

**Lesson Learned**

Interpolation can improve annotation efficiency, but automatically generated bounding-box positions still require manual inspection.

### 3. Case Study 2 — Maintaining Tracking Identity

**Challenge**

Tracking multiple objects requires maintaining the correct identity for each target across frames.

In this project, the four selected targets consisted of two motorcycles and two people.

**Quality Assurance Approach**

Tracking identities were checked during the frame-by-frame review to identify possible identity switches.

**Outcome**

No tracking ID switches were reported within the annotated frame range.

**Lesson Learned**

Consistent object identities are essential for producing reliable video tracking annotations.

### 4. Case Study 3 — Defining Annotation Scope

**Challenge**

The video contains additional road users beyond the four selected targets.

Annotating every visible object would change the scope of this exercise.

**Decision**

The task was limited to two motorcycles and two people. Other visible road users were intentionally excluded.

**Outcome**

The annotation scope remained focused on the four selected tracking targets.

**Lesson Learned**

Annotation quality should be evaluated against the defined project scope rather than the total number of objects visible in a scene.

### 5. Summary of Findings

| QA Finding | Recorded Result |
|---|---|
| Frames reviewed | 51 |
| Selected tracking targets | 4 |
| Interpolation drift issues | 2 |
| Interpolation drift issues corrected | 2 |
| Tracking ID switches | 0 |
| Other bounding-box placement errors | 0 reported |
| Unresolved reported issues | 0 |

### 6. Supporting Evidence

- [Project Overview](README.md)
- [Annotation Guidelines](annotation-guidelines.md)
- [Quality Assurance Report](qa-report.md)
- [CVAT Video Demonstration](https://youtu.be/PD7wA10ZvYc)

### 7. Conclusion

This project demonstrates the importance of manual quality assurance when working with interpolated video annotations.

Two interpolation drift issues were identified and corrected. The review also found no tracking ID switches across the four selected targets.

The exercise highlights practical skills in object tracking, annotation consistency, error detection, and corrective review.
