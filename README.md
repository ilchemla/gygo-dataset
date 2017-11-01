# GyGO: an E-commerce Video Object Segmentation Dataset by Visualead
---

**To get updates as we continually release the dataset, add this project to your "watch" list in github**

## Introduction
GyGO (pronounced jai-go), which release in parts over the following weeks, is a dataset that is focused on a specific, simple use case for video object segmentation: e-commerce.
It will eventually consist of hundreds of short videos and was partly inspired by the release of the DAVIS datasets (link below).

On the one hand, the sequences are quite simple in that they are virtually devoid of occlusions, fast motions or many of the other complexity inducing attributes mentioned above.
On the other hand, the objects in these videos vary wildly in their "semantic categories": toys, cloths, models and office stuff.
The GyGO dataset specializes in smartphone captured videos and its frames are relatively sparse (the annotated video speed is ~5 fps).

We release it publicly with two goals in mind:
- There is a severe lack of data in the space of video object segmentation at the moment.
With only hundreds of annotated videos, we believe every contribution has the potential to increase performance.
In our internal (soon to be published) analysis we have shown that a joint training on the GyGO and DAVIS datasets yields improved inference results. [todo: confirm]
- To promote a more open, sharing culture and encourage other researchers to join our efforts :) The DAVIS dataset and the research ecosystem that grew it have been massively useful for us. We hope the community will find our datasets useful as well.

**Teaser:**

[![IMAGE ALT TEXT](http://img.youtube.com/vi/4RQff9bfJsk/0.jpg)](http://www.youtube.com/watch?v=4RQff9bfJsk "GyGO E-commerce Video Object Segmentation Dataset Teaser")


## Download
 
https://s3.amazonaws.com/gygox-assets/gygo-dataset.tar.gz

Currently the dataset is comprised of **131** training and **24** validation sequences, 
along with their corresponding high quality annotations. 

Each sequence was taken by a handheld smartphone and is 1-10 seconds long. 
The sequences were then decimated to ~5 fps.


## Folder structure
```
.
├── JPEGImages # folders containing RGB videos
|   ├── 480p
|   └── original
├── Annotations # folders containing binary annotations
|   ├── 480p
|   └── original
└── ImageSets
    ├── Train.txt # contains a list of all the sequences for training
    ├── trainval.txt # contains ALL the sequences for training and for validation    
    └── val.txt # contains a list of all the for validation
```

## Benchmarks
TBD

## Links
[Video Object Segmentation — The Basics](https://medium.com/@eddiesmo/video-object-segmentation-the-basics-758e77321914)

[A Meta-analysis of DAVIS-2017 Video Object Segmentation Challenge](https://medium.com/@eddiesmo/a-meta-analysis-of-davis-2017-video-object-segmentation-challenge-c438790b3b56)

[DAVIS Challenge (video object segmentation datasets)](http://davischallenge.org/)

## Contributors
Itamar Friedman,
Ilan Chemla,
Eddie Smolyansky,
Maxim Stepanov,
Irina Afanasyeva,
Gilad Sharir,
Sagi Nadir,
Sagi Rorlich
