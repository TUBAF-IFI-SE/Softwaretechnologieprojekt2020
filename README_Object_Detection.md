# Object Detection Challenge

This repository is a template for participants of the Object Detection Challenge of the RoboCup@Work League.
It resembles one possible starting point for setting up an object detection algorithm.

## Goals of the Challenge

With this challenge we aim at two goals.
Firstly, versatile techniques for detecting objects in 2D camera images exists which may be compared through this challenge.
Secondly, it may serve as a starting point for new teams to enter the field of object detection, which is central for successfully completing most of the tasks within the RoboCup@Work League.

## Prerequisites

The data for training and validating object detectors is available [here](???).

## Evaluation

For evaluating object detectors without restricting teams to certain technologies, only x requirements need to be fulfilled:

1. The detector must read .jpg-images from a given folder
2. The detector must output results for all images in Pascal VOC data format
3. The detector must be callable with the following bash-command:

```
./detector --input <path-to-folder> --output <path-to-folder>
```

## References and First Steps

This section includes a list of links to help you get started with object detection and machine learning in general.
* [Overview on (possible) stages of a Machine Learning Project](https://towardsdatascience.com/10-stages-of-a-machine-learning-project-in-2020-and-where-you-fit-cb73ad4726cb)
* [Image Classification vs. Object Detection](https://www.datacamp.com/community/tutorials/object-detection-guide)
* [Pascal VOC data format](https://towardsdatascience.com/coco-data-format-for-object-detection-a4c5eaf518c5)
