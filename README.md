# GyGO: an E-commerce Video Object Segmentation Dataset by Visualead
---

## Introduction
GyGO (pronounced jai-go) is a video object segmentation dataset focused on e-commerce.
It is currently comprised of **131** training and **24** validation sequences, 
along with their corresponding high quality annotations. 

On the one hand, the sequences are quite simple in that they are virtually devoid of occlusions, fast motions or many of the other complexity inducing attributes mentioned above.
On the other hand, the objects in these videos vary wildly in their semantic categories: toys, cloths, models and office fluff.

Each sequence is 1-10 seconds long and has been captured by a handheld smartphone camera. 
It was then decimated to ~5 fps in post-production and annotated by a non-trivial aggregation of Amazon Mechanical Turk workers.

We release the dataset publicly with two goals in mind:
- There is a severe lack of data in the space of video object segmentation at the moment.
With only hundreds of annotated videos, we believe every contribution has the potential to increase performance.
In our internal (soon to be published) analysis we have shown that a joint training on the GyGO and DAVIS datasets yields improved inference results. [todo: confirm]
- To promote a more open, sharing culture and encourage other researchers to join our efforts :) The DAVIS dataset and the research ecosystem that grew it have been massively useful for us. We hope the community will find our datasets useful as well.

**Teaser:**

[![IMAGE ALT TEXT](http://img.youtube.com/vi/4RQff9bfJsk/0.jpg)](http://www.youtube.com/watch?v=4RQff9bfJsk "GyGO E-commerce Video Object Segmentation Dataset Teaser")


## Download
 
https://gygox-assets.oss-us-east-1.aliyuncs.com/gygo-dataset.tar.gz

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

Attached is a chart of initial benchmarks we have done for the dataset. We consider the works of [OSMN](http://openaccess.thecvf.com/content_cvpr_2018/html/Yang_Efficient_Video_Object_CVPR_2018_paper.html) and [OSVOS](http://www.vision.ee.ethz.ch/~cvlsegmentation/osvos/), as well as our internal networks which were inspired by OSMN and DeeplabV3+. For reference, we add our results on the [DAVIS-2016](https://davischallenge.org/challenge2017/index.html) dataset as well.   

<div class="bi-table">
  <table>
    <colgroup>
      <col width="auto" />
      <col width="auto" />
      <col width="auto" />
      <col width="auto" />
      <col width="auto" />
      <col width="auto" />
      <col width="auto" />
    </colgroup>
    <tbody>
      <tr>
        <td rowspan="1" colSpan="1">
          <div data-type="p">​</div>
        </td>
        <td rowspan="1" colSpan="2">
          <div data-type="p">Zero-shot</div>
        </td>
        <td rowspan="1" colSpan="2">
          <div data-type="p">Zero-shot</div>
        </td>
        <td rowspan="1" colSpan="2">
          <div data-type="p">One-shot, no fine-tuning</div>
        </td>
        <td rowspan="1" colSpan="2">
          <div data-type="p">One-shot, no fine-tuning</div>
        </td>
        <td rowspan="1" colSpan="2">
          <div data-type="p">One-shot with online fine-tuning</div>
        </td>
        <td rowspan="1" colSpan="2">
          <div data-type="p">One-shot with online fine-tuning</div>
        </td>
      </tr>
      <tr>
        <td rowspan="1" colSpan="1">
          <div data-type="p">​</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">Gygo::val</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">DAVIS16::val</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">Gygo::val</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">DAVIS16::val</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">Gygo::val</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">DAVIS16::val</div>
        </td>
      </tr>
      <tr>
        <td rowspan="1" colSpan="1">
          <div data-type="p"><strong>Gygo-OSMN (our implementation)</strong></div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">N/A</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">N/A</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">​96.3% J​</div>
          <div data-type="p">​</div>
          <div data-type="p">7 FPS</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">​80.0% J​</div>
          <div data-type="p">0.797 F</div>
          <div data-type="p">8 FPS</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">​97.2% J​</div>
          <div data-type="p">0.958 F</div>
          <div data-type="p">0.18 FPS</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">​83.2% J​</div>
          <div data-type="p">​</div>
          <div data-type="p">~0.2 FPS</div>
        </td>
      </tr>
      <tr>
        <td rowspan="1" colSpan="1">
          <div data-type="p"><strong>Gygo- Deeplabv3+ (our implementation)</strong></div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">​93.3% J​</div>
          <div data-type="p">​</div>
          <div data-type="p">8.27 FPS</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">​75.9% J​</div>
          <div data-type="p">​</div>
          <div data-type="p">8.53 FPS</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">-</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">-</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">​96.0% J​</div>
          <div data-type="p">​</div>
          <div data-type="p">~0.52 FPS</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">​79.0% J​</div>
          <div data-type="p">​</div>
          <div data-type="p">1.38 FPS</div>
        </td>
      </tr>
      <tr>
        <td rowspan="1" colSpan="1">
          <div data-type="p">Original OSMN (Previous SOTA)</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">-</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">-</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">​95.1% J​</div>
          <div data-type="p">​</div>
          <div data-type="p">7 FPS</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">​73.6% J​</div>
          <div data-type="p">​</div>
          <div data-type="p">8 FPS</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">-</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">-</div>
        </td>
      </tr>
      <tr>
        <td rowspan="1" colSpan="1">
          <div data-type="p">Original OSVOS</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">​</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">​</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">​</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">​</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">93% J</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">79.8% J0.11 FPS on TITAN X (10 min per sequence)</div>
        </td>
      </tr>
    </tbody>
  </table>
</div>

## Links
[Video Object Segmentation — The Basics](https://medium.com/@eddiesmo/video-object-segmentation-the-basics-758e77321914)

[A Meta-analysis of DAVIS-2017 Video Object Segmentation Challenge](https://medium.com/@eddiesmo/a-meta-analysis-of-davis-2017-video-object-segmentation-challenge-c438790b3b56)

The GyGO dataset was drew a lot of inspiration from:

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

## Bibtex
Bibtex:

```
@misc{
author={Friedman, Itamar and Chemla, Ilan and Smolyansky, Eddie and Stepanov, Maxim and Afansyeva, Irina and Sharir, Gilad and Nadir, Sagi and Rorlich, Sagi}, 
title={GyGO: an E-commerce Video Object Segmentation Dataset by Visualead}, 
url={https://github.com/ilchemla/gygo-dataset}, 
year={2017}, month={Sep}}
```
