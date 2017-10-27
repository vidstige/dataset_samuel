# Samuel dataset
A dataset consisting of 64 depth images and a K matrix. The dataset was collected on January 22th 2014 using a Microsoft Kinect device at [Teknikringen 33, Stockholm, Sweden](https://www.google.se/maps/place/Teknikringen+33,+114+28+Stockholm/@59.3495051,18.0712019,17z/data=!3m1!4b1!4m5!3m4!1s0x465f9d6aaad114c3:0xfc92544f835ae96d!8m2!3d59.3495051!4d18.0733906).

## Image format
For easiest possible reading the images are stored, one frame per file, uncompressed. 

Images consists of a fixed size header, 16 bytes long. The raw binary depth data follows as 16-bit unsigned integers.

| Offset | Type   | Meaning |
|--------|--------|---------|
| 0      | uint32 | width   |
| 4      | uint32 | height  |
| 8      | uint32 | stride  |
| 12     | uint32 | one     |

* `width` - width of the image (640)
* `height` - height of the image (480)
* `stride` - byte count of each row (1280)
* `one` - Always set to 1.

After these 16 bytes, follows 614400 bytes of depth data. Each pixel is 16 bits (or two bytes) of unsigned depth data, in row major order.

## K matrix
The K-matrix is stored in the `K.json` json file, and looks like the following.

```json
[
	472, 0, 319.5,
	0, 472, 239.5,
	0, 0, 1
]
```

Where _fx=472_, _fy=472_, _cx=319.5_, _cy=239.5_.

## Author
Samuel Carlsson
