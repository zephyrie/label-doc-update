MONAI Label aims to allow researchers to build labeling applications in a serverless way which means MONAI Label applications are always ready to deploy via the MONAI Label server.

MONAI Label currently provides four template applications that developers may use out-of-the-box or with a few modifications to achieve their desired behavior. You can download any of the sample applications using the MONAI Label CLI.

```
monailabel apps --download --name <sample app name> --output <output folder>
```

The template applications currently available are:

## [Radiology](./radiology)
This app has example models for interactive and automated segmentation over radiology (3D) images. You should refer to this app if you are developing any radiology-related examples. It has examples for the following three types of models.
- DeepEdit (Interactive + Auto Segmentation)
  - Spleen, Liver, Kidney, etc.
- Deepgrow (Interactive)
  - Any Organ/Tissue but pre-trained to work well on Spleen, Liver, Kidney, etc.
- Segmentation (Auto Segmentation)
  - Spleen, Liver, Kidney, etc.

## [Pathology](./pathology)
This app has example models for interactive and automated segmentation over pathology (WSI) images. You should refer to this app if you are developing any pathology-related examples. It has examples for the following two types of models.
- DeepEdit (Interactive + Auto Segmentation)
  - Nuclei Segmentation
- Segmentation (Auto Segmentation)
  - Nuclei multi-label segmentation for
    - Neoplastic cells
    - Inflammatory
    - Connective/Soft tissue cells
    - Dead Cells
    - Epithelial

## [Endoscopy](./endoscopy)
This app has example models for interactive and automated tool tracking segmentation and a classification model for InBody vs. OutBody images.
You should refer to this app if you are developing any endoscopy-related examples. It has examples for the following three types of models.
- DeepEdit (Interactive + Auto Segmentation)
  - Tool Tracking
- Segmentation (Auto Segmentation)
  - Tool Tracking
- Classification
  - InBody vs. OutBody


## [MONAI Bundle](./monaibundle)
MONAI Bundle format defines portable described of deep learning models (docs). A bundle includes the critical information necessary during a model development life cycle and allows users and programs to understand the purpose and usage of the models.

This app has example models for interactive and automated segmentation using monai-bundles defined in [MONAI Model Zoo](https://github.com/Project-MONAI/model-zoo/tree/dev/models). It can pull any bundle defined in the MONAI Model Zoo if compatible and follows the requirements specified on the [MONAI Bundle Apps page](./monaibundle).