# fingerTrackingCourseProject
PPKE ITK Course project for neural networks class

Our project was to create a Vision application for neural networks. The use for this in my case is providing a more natural input for Augmented Reality.
We set a goal, tracking the user's finger in real time, without a teaching process.
We had same requirements as it had to run on a mobile device along with AR processes, also the weights file should be as small as possible.

We created our own dataset as we didn't find any up for this task. It was trained on YOLOv2. We used pre-trained weights on VOC dataset and also used yolo-voc.2.0.cfg as the architecture. We was able to achieve pretty good results. We trained it till 8000 iteration. We got 0.6 average error, and from a test batch it recognised 100% of the objects.

The only drawback the weights' size was, around 500 Mb.

Second time we trained in tiny-yolo (tiny-yolo-voc.cfg) architecture, with the same options described above.
We got less accuracy, but with a weights size as little as 65 Mb.
We was able to test it on a mobile device. I got around 15fps on average.


To test the project:

1. clone and install yolo:
```
git clone https://github.com/pjreddie/darknet
cd darknet
make
```

2. download weights and copy them into root:
* yolo weigths: https://www.dropbox.com/s/k7pw5funuh4jynm/yolo-voc_8000.weights?dl=0
* tiny-yolo weigths: https://www.dropbox.com/s/8zggj6c8okqnihc/tiny-yolo-voc.weights?dl=0

3. run the detection:
```
./darknet detect cfg-path-relative-to-root weights-path-relative-to-root image-path-relative-to-root
```

Example results:

![Single finger](/example1.jpg)

![Multiple finger](/example2.jpg)
