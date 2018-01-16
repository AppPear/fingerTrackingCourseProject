# fingerTrackingCourseProject
PPKE ITK Course project for neural networks class

My project was to create a Vision application for neural networks. The use for this in my case is providing a more natural input for Augmented Reality.
I set a goal, tracking the user's finger in real time, without a teaching process.
I had same requirements as it had to run on a mobile device along with AR processes, also the weights file should be as small as possible.

I created my own dataset as I didn't find any up for this task. Then I trained it on YOLOv2. I used pre-trained weights on VOC dataset. I used yolo-voc.2.0.cfg as the architecture. I was able to achieve pretty good results. I trained it till 8000 iteration. I got 0.6 average error, and from a test batch it recognised 100% of the objects.

The only drawback the weights' size was, around 500 Mb.

Second time I trained in tiny-yolo (tiny-yolo-voc.cfg) architecture, with the same options described above.
I got less accuracy, but with a weights size as little as 65 Mb.
I was able to test it on a mobile device. I got around 15fps on average.


To test my project:

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
