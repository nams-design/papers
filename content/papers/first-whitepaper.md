+++
date = '2025-12-09T13:32:44+05:30'
draft = true
title = 'first whitepaper'
+++

<<draft summary: cutting down the time to annotate>>

- we are making a new dataset for sarees and indowestern (all types- blouse, shawl, jacket, co-ord sets)
- trying to streamline to create a dataset by using yolo sam2.1 (segmentation model) which helps us to one click select a section and label it so that it creates polygons automatically by itself rather than us selecting each and every point 
- when a sizeable amt of dataset is created were using it to train a yolo v11 instance segmentation model 
- we are then using this model to segment the sarees and indowesterns in real time, basically cutting down the time to an image from around 1 min-> few seconds
- autoannotating the dataset using yolo sam2.1 & yolo v11 instance segmentation model (fully automated)
- conclusion - we have successfully created a dataset for sarees and indowesterns and trained a yolo v11 instance segmentation model on it. we are now using this model to segment the sarees and indowesterns in real time. we have also autoannotated the dataset using yolo sam2.1 & yolo v11 instance segmentation model (fully automated). indian dresses dont have a surplus amount of dataset available so were creating out own for our usage.

Draft
## Accelerating Indian Fashion Dataset Creation with the Help of A YOLO-Powered Pipeline for High-Speed Image Annotation

## Abstract
The creation of large-scale, accurately annotated image datasets is a significant bottleneck in the development of fashion-focused AI applications. This is particularly true for diverse and intricate apparel categories such as sarees and kurtas, along with Indo-western wear which includes jackets, co-ord sets, shawls, stoles and dresses. 
This whitepaper introduces a novel pipeline that dramatically accelerates the annotation process by integrating one-click segmetation capabilities of yolo-sam2.1 for the initial dataset creation and then leveraging with a custom-trained powerful instance segmentation model, yolo v11 to develop a system for real-time automated annotations. This approach reduces the time taken to annotate a single image from approximately 1 minute to mere seconds, paving the way for the rapid development of robust fashion AI models.
## Introduction: The Annotation Bottleneck in Fashion AI
- The Challenge: Feature Advancements in Fashion AI such as virtual try ons,style recommendations, and precise searches are fundamentally constrained by the availability of large, accurately annotated datasets, This bottleneck is acutely severe for culturally specific and structurally complex garments like sarees, blouses, co-ord sets, shawls, stoles, jackets, and layered indo-western outfits. Traditional polygon based annotation is time-consuming and labor intensive, often requiring approximately 1 minute per item for precise point by point boundary demarcations. The scarcity of such datasets for Indian attire stifles innovation and limits the global reach of these fashion categories. 
- The Oppurtunity: A robust, automatically generated dataset for these specific complex garments unlock transformative applications such as hyper-realistic virtual try-ons for saree drapes, intelligent styling of co-ord sets, and discoverability of trending intricate Indo-western designs. The solution lies in overcoming the initial annotation hurdle to create a self-reinforcing data generation cycle.
- Our Solution: We introduce a novel pipeline that combines state-of-the-art segmentation models to first streamline and then fully automate the annotation process. For rapid, semi-automated dataset creation, we first utilize YOLO-SAM2.1. This initial dataset then fuels the training of a purpose-built YOLOv11 instance segmentation model, resulting in the formation of a system that is capable of real-time, fully automatic annotations.

## Streamlining Initial Annotation with YOLO-SAM2.1
- Introduction to YOLO-SAM2.1: In the realm of interactive segmentation, YOLO-SAM2.1 stands out for its ability to segment objects in images with remarkable precision. This model combines the object detection powers of YOLO (You Only Look Once) with the zero-shot segmentation capability of Segment Anything Model(SAM) enabling users to segment objects with a single click. For our use case, its one-click segmentation is revolutionary because this not only saves significant time but also ensures high accuracy in the segmentation process. 
- The Process: Instead of having to manually plot numerous polygon points, an annotator simply opens and image and clicks once on a target garment and the YOLO-SAM2.1 model instantly generates a high-fidelity mask around the item, eliminating the need for manual precision. This accelerates the annotation process while also ensuring that the masks are of the highest quality.
- Immediate Benefits: This single step alone reduces the manual effort per item by over 90% thus speeding up the dataset creation process. The annotator's role then shifts from a meticulous draftsman to a supervisor who verifies and occasionally refines the model outputs by validating the initial masks, which is a much more manageable task as compared to pixel-by-pixel

## Building the Automation Engine: a Custom YOLOv11 Model
- Building a Foundation: The curated dataset that is generated via YOLO-SAM2.1 is the cornerstone of our automation pipeline. This generated dataset comprises of thousands of annotated sarees and indo-western items to ensure high quality and diversity, with a particular focus on the complex garment categories and subcategories. This curated dataset serves as the high- quality training ground for our custom YOLOv11 instance segmentation model.

- Why YOLOv11? We have selected YOLOv11 for its optimal balance of inference speed, accuracy and maturity in instance segmentation tasks. This state-of-the-art model has been extensively tested and validated in the industry, making it a reliable choice for our automation pipeline. Its architecture is also ideally suited for moving from interactive annotation to a pure, forward-pass automation model that can run in real-time.

- The Training: We have trained the YOLOv11 model on our growing dataset by continuously incorporationg new annotations as they are generated. This iterative training process ensures that the model remains up-to-date and accurate, adapting to the evolving needs of our users. This continuous feedback loop is essential for maintaining the high standards of our automated annotations. The phase focuses on teaching the model the distinct visual features and structural complexities of our targeted categories such as the type of embroidery present in a saree to the structured silhoutte of a co-ord set with jacket.

## Achieving Real-Time, Fully Automated Annotations
-