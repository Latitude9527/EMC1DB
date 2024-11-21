# Enhanced YOLOv10-N: A lightweight YOLOv10 with Efficient Multi-Scale Cross 1D Convolutions

  <summary>
  <font size="+1">Abstract</font>
  </summary>
Convolutional neural networks (CNNs) are known for their ability to learn and recognize various objects and patterns, which makes them be powerful feature extractors. While 2D convolutions used in CNNs are effective for extracting features from images, their large convolutional kernels, such as  $7\times7$ kernel, often result in more parameters. This makes them unsuitable for small object detection models deployed on devices with limited computational resources. However, simply using 1D convolution with fewer parameters in the model of object detection will lead to a performance degradation. To address this issue, we propose an efficient multi-scale cross 1D convolutional block (EMC1DB), which has stronger feature extraction capabilities, thereby improving the performance of small object detection models. Additionally, in order to address the problem of inaccurate bounding box localization in object detection, we introduce a modified bounding box regression loss function named Anchored IoU loss (AIoU),  which improves sensitivity to precise bounding box matching. Combining the above two plug-and-play EMC1DB and AIoU in YOLOv10-N enables it to achieve higher performance than the baseline on PASCLA VOC 2012 and MS COCO 2017 datasets. In addition, experimental results show that the proposed method also performs well in YOLOv7-T.
</details>


## Installation
`conda` virtual environment is recommended. 
```
conda create -n yolov10 python=3.9
conda activate yolov10
pip install -r requirements.txt
pip install -e .
```


## Validation
[`yolov10n.pt`](https://github.com/THU-MIG/yolov10/releases/download/v1.1/yolov10n.pt)  [`yolov10s.pt`](https://github.com/THU-MIG/yolov10/releases/download/v1.1/yolov10s.pt)  [`yolov10m.pt`](https://github.com/THU-MIG/yolov10/releases/download/v1.1/yolov10m.pt)  [`yolov10b.pt`](https://github.com/THU-MIG/yolov10/releases/download/v1.1/yolov10b.pt)  [`yolov10l.pt`](https://github.com/THU-MIG/yolov10/releases/download/v1.1/yolov10l.pt)  [`yolov10x.pt`](https://github.com/THU-MIG/yolov10/releases/download/v1.1/yolov10x.pt)  
```
yolo val model=yolov10n/s/m/b/l/x.pt data=coco.yaml batch=256
```

## Training 
```
yolo detect train data=coco.yaml model=yolov10n/s/m/b/l/x.yaml epochs=500 batch=256 imgsz=640 device=0,1,2,3,4,5,6,7
```

## Prediction
```
yolo predict model=yolov10n/s/m/b/l/x.pt
```

## Acknowledgement
The code base is built with ultralytics， RT-DETR and YOLOv10.
Thanks for the great implementations!

This work was supported by the Key R&D Program of Shandong Province, China (2024TSGC0109)

## Citation

If our code or models help your work, please cite our paper:
```BibTeX

```
