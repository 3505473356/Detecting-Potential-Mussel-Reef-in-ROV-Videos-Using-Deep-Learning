# Detecting-Potential-Mussel-Reef-in-ROV-Videos-Using-Deep-Learning
### Xinyu Liu, s212632; Weisen Yu, s222463

## Introduction to the project
Blue mussel reefs are listed as biogenic reefs in the Habitat Directive of the European Union. They can protect shorelines and function as habitats for many marine creatures, but they are in danger. To protect existing mussel reefs, it is necessary first to find mussels and then map them to confirm that they form a mussel reef. DTU Aqua uses ROV(remotely operated vehicle) to film seabed and map mussel reefs based on ROV videos. We propose one method based on YOLO(You Only Look Once) algorithm to detect mussels in the videos, roughly estimate their coverage automatically, and indicate potential mussel reefs. Additionally, one dataset, including 1000 labeled mussel images, was constructed to bridge the gap in marine datasets.

## Introduction to the files

`03-02_16.07.53`: The name is the video's name. It contains all the .npy files corresponding to all mussels' coverage in all frames in the video.

`yolov5_modified`: It includes all the code and trained model: `best.pt`.

`Image_segmentation`: 

`PostProcess.ipynb`: It is used to load mussels' coverage information in the video and adjust unreasonable data, finally doing result visulization.

`Poster.pdf` and `Report.pdf` are the poster and report to this project.

`test_images`: It contains three images can be used as `source` input to `detect.py` for mussel detection.

`example.gif`: It is the clip of the output video after detection. The complete video is very big around 8G nearly thirty minutes.

![example](https://github.com/3505473356/Detecting-Potential-Mussel-Reef-in-ROV-Videos-Using-Deep-Learning/blob/main/example.gif)

## How to use the system

Firstly, download the YOLO code `yolov5_modified`, and use `detect.py` to detect and mark mussels in videos with rectangles. Same as the turtorial in the https://github.com/ultralytics/yolov5/blob/master/tutorial.ipynb. For example, "python detect.py --weights best.pt(trained model) --source xxxxx(path of video)".

Secondly, one file named by the video's name is created, it includes .npy files, the number of them is the number of frames in the video.

Thirdly, run the `PostProcess.ipynb`, set visulization parameters and output the result.

For segmentation, using code in ` ` and run ` .py` in `Image segmentation`.
