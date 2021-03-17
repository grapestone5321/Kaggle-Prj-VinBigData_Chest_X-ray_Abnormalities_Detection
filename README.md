# Kaggle-Prj-VinBigData_Chest_X-ray_Abnormalities_Detection
Kaggle-Prj-VinBigData_Chest_X-ray_Abnormalities_Detection


-------

## Task

In this competition, you’ll automatically localize and classify 14 types of thoracic abnormalities from chest radiographs. 

You'll work with a dataset consisting of 18,000 scans that have been annotated by experienced radiologists. 

You can train your model with 15,000 independently-labeled images and will be evaluated on a test set of 3,000 images.


-------

## Final Submission Deadline:
March 30, 2021

Deadline is at 11:59 PM UTC 

-------

## Evaluation

The challenge uses the standard PASCAL VOC 2010 mean Average Precision (mAP) at IoU > 0.4.

-------

## Dataset information

The dataset comprises 18,000 postero-anterior (PA) CXR scans in DICOM format, which were de-identified to protect patient privacy. 

All images were labeled by a panel of experienced radiologists for the presence of 14 critical radiographic findings as listed below:

      0 - Aortic enlargement
      1 - Atelectasis
      2 - Calcification
      3 - Cardiomegaly
      4 - Consolidation
      5 - ILD
      6 - Infiltration
      7 - Lung Opacity
      8 - Nodule/Mass
      9 - Other lesion
      10 - Pleural effusion
      11 - Pleural thickening
      12 - Pneumothorax
      13 - Pulmonary fibrosis

The "No finding" observation (14) was intended to capture the absence of all findings above.

Note that a key part of this competition is working with ground truth from multiple radiologists.


-------

## Papers

### VinDr-CXR: An open dataset of chest X-rays with radiologist's annotations
https://arxiv.org/pdf/2012.15029.pdf

### ABSTRACT
      Most of the existing chest X-ray datasets include labels from a list of findings without specifying their locations 
      on the radiographs.
      This limits the development of machine learning algorithms for the detection and localization of chest abnormalities. 
      In this work, we describe a dataset of more than 100,000 chest X-ray scans that were retrospectively collected 
      from two major hospitals in Vietnam. 
      Out of this raw data, we release 18,000 images that were manually annotated by a total of 17 experienced radiologists
      with 22 local labels of rectangles surrounding abnormalities and 6 global labels of suspected diseases. 
      The released dataset is divided into a training set of 15,000 and a test set of 3,000. 
      Each scan in the training set was independently labeled by 3 radiologists, while each scan in the test set was labeled 
      by the consensus of 5 radiologists. 
      We designed and built a labeling platform for DICOM images to facilitate these annotation procedures. 
      All images are made publicly available in DICOM format in company with the labels of the training set. 
      The labels of the test set are hidden at the time of writing this paper as they will be used for benchmarking machine 
      learning algorithms on an open platform.

-------


## VinBigData 2-class classifier complete pipeline
https://www.kaggle.com/corochann/vinbigdata-2-class-classifier-complete-pipeline




       Public Score: 0.223


-------


