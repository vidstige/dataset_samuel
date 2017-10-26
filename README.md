# Samuel dataset
A dataset consisting of 64 depth images and a K matrix. The dataset was collected on January 22th 2014 using a Microsoft Kinect device.

## Image format
For easiest possible reading the images are stored, one frame per file, uncompressed. 

Images consists of a fixed size header, 16 bytes long. The raw binary depth data follows as 16-bit unsigned integers.

| Offset | Type   |        |
|--------|--------|--------|
| 0      | uint32 | width  |
| 4      | uint32 | height |
| 8      | uint32 | stride |
| 12     | uint32 | one    |

After these 16 bytes, follows 614400 bytes of depth data. Each pixel is 16 bits or two bytes of unsigned depth data, in row major order.

## K matrix
The K-matrix is stored in the `K.json` json file, and looks like the following.

```json
[
	472, 0, 319.5,
	0, 472, 239.5,
	0, 0, 1
]
```

Where fx=472, fy=472, cx=319.5, cy=239.5.

## Author
Samuel Carlsson
