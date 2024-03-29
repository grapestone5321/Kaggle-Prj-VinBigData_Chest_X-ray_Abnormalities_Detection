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

The challenge uses the standard PASCAL VOC 2010 **mean Average Precision (mAP)** at IoU > 0.4.

### The PASCAL Visual Object Classes Challenge 2010 (VOC2010) Development Kit
http://host.robots.ox.ac.uk/pascal/VOC/voc2010/devkit_doc_08-May-2010.pdf

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

## Visual Object Classes Challenge 2010 (VOC2010)
http://host.robots.ox.ac.uk/pascal/VOC/voc2010/




-------

## Website
https://vindr.ai/vinlab


## Papers

### 1. VinDr-CXR: An open dataset of chest X-rays with radiologist's annotations
https://arxiv.org/pdf/2012.15029.pdf

### ABSTRACT
      Most of the existing chest X-ray datasets include labels from a list of findings without specifying 
      their locations on the radiographs.
      This limits the development of machine learning algorithms for the detection and localization of 
      chest abnormalities. 
      In this work, we describe a dataset of more than 100,000 chest X-ray scans that were retrospectively 
      collected from two major hospitals in Vietnam. 
      Out of this raw data, we release 18,000 images that were manually annotated by a total of 17 
      experienced radiologists with 22 local labels of rectangles surrounding abnormalities and 6 global 
      labels of suspected diseases. 
      The released dataset is divided into a training set of 15,000 and a test set of 3,000. 
      Each scan in the training set was independently labeled by 3 radiologists, while each scan in the 
      test set was labeled by the consensus of 5 radiologists. 
      We designed and built a labeling platform for DICOM images to facilitate these annotation procedures. 
      All images are made publicly available in DICOM format in company with the labels of the training set. 
      The labels of the test set are hidden at the time of writing this paper as they will be used for 
      benchmarking machine learning algorithms on an open platform.

### 2. CheXNet: Radiologist-Level Pneumonia Detection on Chest X-Rays with Deep Learning
https://arxiv.org/pdf/1711.05225.pdf

### 3. CheXpedition: Investigating Generalization Challenges for Translation of Chest X-Ray Algorithms to the Clinical Setting
https://arxiv.org/pdf/2002.11379.pdf


### 4. Interpreting chest X-rays via CNNs that exploit hierarchical disease dependencies and uncertainty labels
https://arxiv.org/pdf/1911.06475.pdf

### 5. PADCHEST: A LARGE CHEST X-RAY IMAGE DATASET WITH MULTI-LABEL ANNOTATED REPORTS
https://arxiv.org/pdf/1901.07441.pdf


### 6. CheXbert: Combining Automatic Labelers and Expert Annotations for Accurate Radiology Report Labeling Using BERT
https://arxiv.org/pdf/2004.09167.pdf

-------

## Progress

### Public Best LB Score: 0.246

### Private Score: 0.226




-------


## VinBigData 2-class classifier complete pipeline
https://www.kaggle.com/corochann/vinbigdata-2-class-classifier-complete-pipeline

## VinBigData_2-class_classifier_complete_pipeline-2

### optimizer: lr=1e-3: default

       lr=1e-1     LB 0.223  vsr7
       lr=1e-2     LB 0.223  vsr6
       lr=1e-3     LB 0.223  vsr5
       
### Data config
      imgdir_name: str = "vinbigdata-chest-xray-resized-png-256x256"
      # split_mode: str = "all_train"  # all_train or valid20

lr=1e-3:

      seed: int = 111      LB 0.223   vsr5
      seed: int = 42       LB 0.223   vsr8

### Training config
      epoch: int = 20      LB 0.223   vsr5
      epoch: int = 30      LB 0.223   vsr9
      


-------

## VinBigData-CXR-AD YOLOv5 14 Class [train]
https://www.kaggle.com/awsaf49/vinbigdata-cxr-ad-yolov5-14-class-train


-------     

## VinBigData-CXR-AD YOLOv5 14 Class [infer]
https://www.kaggle.com/awsaf49/vinbigdata-cxr-ad-yolov5-14-class-infer

### !python detect.py --weights $weights_dir\

      --conf 0.15:    LB  0.148    ver1
      --conf 0.01:    LB  0.152    ver4    
      
### dim = 512 #1024, 256, 'original'
      test_dir = f'/kaggle/input/vinbigdata-{dim}-image-dataset/vinbigdata/test'

--conf 0.01: 

      dim = 'original'       LB 00.146, error     ver7
      dim = 256              LB 0.125             ver6
      dim = 512              LB 0.152             ver4
      dim = 1024             LB 0.152             ver5

-------

## VinBigData 🌟2 Class Filter🌟
https://www.kaggle.com/awsaf49/vinbigdata-2-class-filter

- 2 Class Filter

      Previously I have trained YOLOv5 using 14 class data. 
      As it creates FP we can tackle that just simply using a 2 class filter. 
      Here I'll be using 2 class model (AUC:0.98) prediction to filter out the FP predictions. 
      I used EfficientNetB6 to generate these predictions. 
      It should increase the score as FP would be reduced significantly

### VinBigData 2-class Prediction: Dataset
https://www.kaggle.com/awsaf49/vinbigdata-2class-prediction

      pred_2cls = pd.read_csv('../input/vinbigdata-2class-prediction/2-cls test pred.csv')

### pred_14cls = pd.read_csv

low_thr, high_thr = 0.08, 0.95:

      vinbigdata-14-class-submission-lb0154/submission.csv (LB 0.154):       LB 0.211   ver1
      vinbigdatastack/submission_postprocessed.csv (LB 0.239):               LB 0.243   ver3 
      vinbigdatastack/submission.csv (LB 0.241):                             LB 0.244   ver10
      vinbigdatastack/submission (1).csv (LB 0.235)                          LB 0.241   ver11  
      
      vinbigdatasubmissions1/submission-0246-ens-ver7.csv (LB 0.246):        LB 0.246   ver12      147 -> 147       --- Best 
      vinbigdatasubmissions1/submission-0243-muhammad.csv (LB 0.243):        LB 0.244   ver14     
      
      vinbigdatasubmissions1/submission-0246-old.csv (LB 0.246):             LB 0.246   ver15      151 -> 151
      vinbigdatasubmissions1/submission2-0246-mahmud.csv (LB 0.246):         LB 0.246   ver16      151 -> 151

      vinbigdatasubmissions1/submission-0244-2clfil-ver10.csv (LB 0.246):    LB 0.244   ver18 


### low_thr, high_thr: default = 0.08, 0.95

vinbigdatastack/submission_postprocessed.csv (LB 0.239):
      
high_thr = 0.87:

      low_threshold = 0.0     LB 0.236   vsr5
      
high_thr = 0.95:

      low_threshold = 0.09     LB 0.242   ver7
      low_threshold = 0.08     LB 0.243   ver3
      low_threshold = 0.07     LB 0.242   ver6   
      
low_thr  = 0.08:

      high_thr = 0.97    LB 0.243   ver9
      high_thr = 0.95    LB 0.243   ver3
      high_thr = 0.93    LB 0.243   ver8 
      high_thr = 0.87    LB 0.243   ver4 
         
pred_14cls = pd.read_csv('/kaggle/input/vinbigdatasubmissions1/submission-0246-ens-ver7.csv'):

      if prob<low_thr:, elif low_thr<=prob<high_thr:, elif high_thr<=prob:      LB 0.246   ver12    --- Best
      if prob<=low_thr:, elif low_thr<prob<high_thr:, elif high_thr<=prob:      LB 0.246   ver17 

-------

## Ensemble of best public notebooks
https://www.kaggle.com/saurabhbagchi/ensemble-of-best-public-notebooks

### low_threshold, high_threshold: default = 0.0, 0.90

low_threshold = 0.0:

      high_threshold = 0.85    LB 0.207   ver3
      high_threshold = 0.86    LB 0.245   ver8
      high_threshold = 0.87    LB 0.246   ver7   --- Best  132 -> 127
      high_threshold = 0.88    LB 0.246   ver6             132 -> 132
      high_threshold = 0.89    LB 0.246   ver5 
      high_threshold = 0.90    LB 0.244   ver1
      high_threshold = 0.91    LB 0.243   ver4
      high_threshold = 0.95    LB 0.241   ver2
      
high_threshold = 0.87:

      low_threshold = 0.0     LB 0.246   ver7   --- Best
      low_threshold = 0.01    LB 0.246   ver15            131 -> 131
      low_threshold = 0.02    LB 0.246   ver14            131 -> 131
      low_threshold = 0.05    LB 0.246   ver12            131 -> 131
      low_threshold = 0.08    LB 0.246   ver13            131 -> 131
      low_threshold = 0.10    LB 0.246   ver11            131 -> 131 
      low_threshold = 0.20    LB 0.246   ver10            127 -> 127      
      low_threshold = 0.50    LB 0.246   ver9             127 -> 127


high_threshold = 0.87, low_threshold = 0.0:
      
      vinbigdatastack/submission_postprocessed.csv (LB 0.239):                LB 0.246   ver7   --- Best
      vinbigdatastack/submission.csv (LB 0.241):                              LB 0.245   ver16
      vinbigdatastack/submission (1).csv (LB 0.235)                           LB 0.244   ver17
      
      vinbigdata-14-class-submission-lb0154/submission.csv (LB 0.154)         LB 0.208   ver18 
      
      vinbigdatasubmissions1/submission-0244-2clfil-ver10.csv (LB 0.244):     LB 0.246   ver19      147 -> 147  
      vinbigdatasubmissions1/submission-0243-muhammad.csv (LB 0.243):         LB 0.245   ver20      
      vinbigdatasubmissions1/submission-0246-old.csv (LB 0.246):              LB 0.245   ver21 
      vinbigdatasubmissions1/submission2-0246-mahmud.csv (LB 0.246):          LB 0.245   ver22 

pred_det_df = pd.read_csv("../input/vinbigdatastack/submission_postprocessed.csv"):

    if p0 < low_threshold:, elif low_threshold <= p0 and p0 < high_threshold:       LB 0.246   ver7   --- Best
    if p0 < low_threshold:, elif low_threshold <= p0 and p0 <= high_threshold:      LB 0.246   ver24 
    if p0 <= low_threshold:, elif low_threshold < p0 and p0 < high_threshold:       LB 0.246   ver25 

-------

## VinBigData-submission

      df1 = pd.read_csv('/kaggle/input/vinbigdatastack/submission_postprocessed.csv')     LB 0.239   ver2
      df1 = pd.read_csv('/kaggle/input/vinbigdatastack/submission.csv')                   LB 0.241   ver3
      df1 = pd.read_csv('/kaggle/input/vinbigdatastack/submission (1).csv')               LB 0.235   ver4

      df2 = pd.read_csv('/kaggle/input/vinbigdata-14-class-submission-lb0154/submission.csv')    LB 0.154   ver5  

-------


