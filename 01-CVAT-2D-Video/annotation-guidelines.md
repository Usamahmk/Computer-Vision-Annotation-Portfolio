# Annotation Guidelines
## CVAT 2D Object Tracking Project

### 1. Project Objective

The objective of this project is to track four selected road users across video frames using CVAT.

The selected objects are:

- 2 motorcycles
- 2 people

This is a targeted tracking exercise. Other visible road users are outside the annotation scope.

### 2. Annotation Configuration

| Parameter | Specification |
|---|---|
| Annotation Tool | CVAT |
| Task Type | Video Object Tracking |
| Annotation Shape | Rectangle |
| Frame Range | 0–50 |
| Total Frames | 51 |
| Keyframe Interval | 10 frames |
| Keyframes | 0, 10, 20, 30, 40, 50 |
| Object Classes | Motorcycle, Person |
| Selected Objects | 4 |
| Tracking Method | Manual keyframes with interpolation |

### 3. Object Classification Rules

**Motorcycle**

Assign the `Motorcycle` label to each of the two selected motorcycles. Keep the label consistent across the annotated sequence.

**Person**

Assign the `person` label to each of the two selected people. Maintain the same classification as each person moves through the video.

Do not introduce additional classes or annotate unrelated objects outside the selected tracking targets.

### 4. Bounding Box Placement Rules

- Position the bounding box closely around the visible extent of the selected object.
- Avoid unnecessary background space inside the rectangle.
- Update the bounding box when the object's position, apparent size, or orientation changes.
- Keep the box aligned with the correct target.
- Review small or partially obscured objects carefully.
- Use consistent placement rules across frames.

### 5. Keyframe and Interpolation Rules

Manual keyframes are placed at:

**0 → 10 → 20 → 30 → 40 → 50**

CVAT interpolation is used to estimate bounding-box positions between these keyframes.

Every intermediate frame must be reviewed to identify interpolation drift or inaccurate placement.

When interpolation drift occurs, correct the affected bounding-box position and verify the surrounding frames. Add or adjust keyframes where necessary to maintain accurate tracking.

### 6. Object Identity Rules

Each selected target must maintain a consistent tracking identity throughout its annotated trajectory.

- Do not assign an existing object's track to another object.
- Do not switch identities when two targets move close to each other.
- Do not create duplicate tracks for the same selected target.
- Verify identity consistency during frame-by-frame review.

### 7. Occlusion and Visibility Rules

When a target becomes partially hidden, adjust the annotation according to its visible position and the applicable project guidelines.

If a target becomes fully invisible, do not invent its location. Use CVAT's visibility or outside-state controls as appropriate to the task.

When the target reappears, verify its identity before continuing the track.

### 8. Quality Assurance Procedure

After annotation:

1. Review all 51 frames individually.
2. Verify motorcycle and person labels.
3. Check bounding-box alignment.
4. Inspect the intermediate frames for interpolation drift.
5. Confirm that tracking identities remain consistent.
6. Correct identified issues.
7. Review the affected frames after correction.
8. Record the QA results.

### 9. Recorded QA Findings

| QA Metric | Result |
|---|---|
| Frames reviewed | 51 |
| Tracking ID switches | 0 |
| Other bounding-box placement errors | 0 reported |
| Interpolation drift issues identified | 2 |
| Interpolation drift issues corrected | 2 |
| Unresolved identified issues | 0 reported |

These results are based on the manual QA review of the four selected targets within frames 0–50.

### 10. Supporting Evidence

- [View the QA Report](qa-report.md)
- [View the Project README](README.md)
- [Watch the CVAT Tracking Demonstration](https://youtu.be/PD7wA10ZvYc)

### 11. Conclusion

These guidelines define the labeling, tracking, interpolation, and quality assurance procedures for the targeted CVAT 2D tracking exercise.

The project demonstrates structured annotation practices, consistent object identification, and the ability to detect and correct interpolation issues.
