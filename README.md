# Distance Estimation
The function estimates distance in a mp4 video. I tested it on dashcam videos from Youtube.

## Function

```python
def estimate_distance(bbox_width):
    focal_length = 1000  # Example focal length in pixels
    known_width = 2.0  # Known width of the vehicle in meters
    distance = (known_width * focal_length) / bbox_width
    return distance
```

## Explanation
The logic behind this distance estimation is processing of video frame by frame. The frame window is considered as the camera and distance in pixels is estimated from the objects in the video that move frame by frame. 

When using the function in image callback or process video functions:

``` python
bbox_width = x2 - x1
distance = estimate_distance(bbox_width)
```

## Example:
<div align="center">
  <img src="https://github.com/user-attachments/assets/b9699003-7a4f-4a78-ae45-263009398bca" alt="Example Image" width="700" />
</div>


<div align="center">
  <img src="https://github.com/user-attachments/assets/9703ce8e-b691-4c12-9e15-292caaef87bc" alt="Example Image" width="700" />
</div>

## Note:
The images were taken from [UDACITY](https://github.com/UDACITY).
