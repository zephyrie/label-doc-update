<!--
Copyright (c) MONAI Consortium
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at
    http://www.apache.org/licenses/LICENSE-2.0
Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
-->

# MONAI Label
[![License](https://img.shields.io/badge/license-Apache%202.0-green.svg)](https://opensource.org/licenses/Apache-2.0)
[![CI Build](https://github.com/Project-MONAI/MONAILabel/workflows/build/badge.svg?branch=main)](https://github.com/Project-MONAI/MONAILabel/commits/main)
[![Documentation Status](https://readthedocs.org/projects/monailabel/badge/?version=latest)](https://docs.monai.io/projects/label/en/latest/?badge=latest)
[![PyPI version](https://badge.fury.io/py/monailabel.svg)](https://badge.fury.io/py/monailabel)
[![Azure DevOps tests (compact)](https://img.shields.io/azure-devops/tests/projectmonai/monai-label/10?compact_message)](https://dev.azure.com/projectmonai/monai-label/_test/analytics?definitionId=10&contextType=build)
[![Azure DevOps coverage](https://img.shields.io/azure-devops/coverage/projectmonai/monai-label/10)](https://dev.azure.com/projectmonai/monai-label/_build?definitionId=10)
[![codecov](https://codecov.io/gh/Project-MONAI/MONAILabel/branch/main/graph/badge.svg)](https://codecov.io/gh/Project-MONAI/MONAILabel)

MONAI Label is a server-client system that facilitates interactive medical image annotation by using AI. It is an
open-source and easy-to-install ecosystem that can run locally on a machine with single or multiple GPUs. Both server
and client work on the same/different machine. It shares the same principles
with [MONAI](https://github.com/Project-MONAI). 

Refer to full [MONAI Label documentations](https://docs.monai.io/projects/label/en/latest/index.html) for more details.

[What is MONAI Label?](https://youtu.be/m2rYorVwXk4) | [MONAI Label Deep Dive Videos](https://www.youtube.com/playlist?list=PLtoSVSQ2XzyD4lc-lAacFBzOdv5Ou-9IA)

### Table of Contents
- [Highlights and Features](#hightlights)
- [Supported Apps, Viewers, and Data](#supported-features)
- [Installation and Usage](#installation)
  - [MONAI Label Server](#current-stable-version)
  - [Visualization Tools Guide](#visualization-tools)
  - [Plugin Guide](#plugins)
- [MONAI Label Sample Applications](#monailabel-sample-applications)
- [MONAI Label Viewer Integrations](#monailabel-viewer-integrations)
- [Contributing Guide and Communities](#contributing)

### Highlights and Features
- Framework for developing and deploying MONAI Label Apps to train and infer AI models
- Compositional & portable APIs for ease of integration in existing workflows
- Customizable labeling app design for varying user expertise
- Annotation support via [3DSlicer](https://github.com/Project-MONAI/MONAILabel/tree/main/plugins/slicer)
  & [OHIF](https://github.com/Project-MONAI/MONAILabel/tree/main/plugins/ohif) for radiology
- Annotation support via [QuPath](https://github.com/Project-MONAI/MONAILabel/tree/main/plugins/qupath), [Digital Slide Archive](https://github.com/Project-MONAI/MONAILabel/tree/main/plugins/dsa), and [CVAT](https://github.com/Project-MONAI/MONAILabel/tree/main/plugins/cvat) for
  pathology
- Annotation support via [CVAT](https://github.com/Project-MONAI/MONAILabel/tree/main/plugins/cvat) for Endoscopy
- PACS connectivity via [DICOMWeb](https://www.dicomstandard.org/using/dicomweb)
- Automated Active Learning workflow for endoscopy using [CVAT](https://github.com/Project-MONAI/MONAILabel/tree/main/plugins/cvat)

### Supported Apps, Viewers, and Data
<table>
<tr>
  <th>Field</th>
  <th>Apps</th>
  <th>Viewers</th>
  <th>Data Types</th>
  <th>Modalities/Target</th>
</tr>
  <td>Radiology</td>
  <td>
    <ul>
      <li>DeepEdit</li>
      <li>DeepGrow</li>
      <li>Segmentation</li>
      <li>MONAI Bundles</li>
    </ul>
  </td>
  <td>
    <ul>
      <li>3D Slicer</li>
      <li>OHIF</li>
    </ul>
  </td>
  <td>
    <ul>
      <li>nifti</li>
      <li>DICOM</li>
    </ul>
  </td>
  <td>
    <ul>
      <li>X-Ray</li>
      <li>CT</li>
      <li>MRI</li>
    </ul>
  </td>
<tr>
</tr>
  <td>Pathology</td>
  <td>
    <ul>
      <li>DeepEdit</li>
      <li>NuClick</li>
      <li>Segmentation</li>
      <li>MONAI Bundles</li>
    </ul>
  </td>
  <td>
    <ul>
      <li>Digital Slide Archive</li>
      <li>QuPath</li>
      <li>CVAT</li>
    </ul>
  </td>
  <td>
    <ul>
      <li>TIFF</li>
      <li>SVS</li>
    </ul>
  </td>
  <td>
    <ul>
      <li>Nuclei Segmentation</li>
      <li>Nuclei Classification</li>
    </ul>
  </td>
<tr>
</tr>
  <td>Endoscopy</td>
  <td>
    <ul>
      <li>DeepEdit</li>
      <li>Tooltracking</li>
      <li>InBody</li>
      <li>MONAI Bundles</li>
    </ul>
  </td>
  <td>
    <ul>
      <li>CVAT</li>
    </ul>
  </td>
  <td>
    <ul>
      <li>JPG</li>
      <li>3-channel Video Frames</li>
    </ul>
  </td>
  <td>
  </td>
<tr>
</table>

# Getting Started with MONAI Label
### MONAI Label requires a few steps to get started:
- Step 1: Install MONAI Label
- Step 2: Download a MONAI Label sample app or write your own custom app
- Step 3: Install a compatible viewer and supported MONAI Label Plugin
- Step 4: Prepare your Data
- Step 5: Launch MONAI Label Server and start Annotating!

## Installation

### Current Stable Version
<a href="https://pypi.org/project/monailabel/#history"><img alt="GitHub release (latest SemVer)" src="https://img.shields.io/github/v/release/project-monai/monailabel"></a>
<pre>pip install -U monailabel</pre>

MONAI Label supports the following OS with **GPU/CUDA** enabled. For more details instruction, please see the installation guides.
- [Ubuntu](https://docs.monai.io/projects/label/en/latest/installation.html)
- [Windows](https://docs.monai.io/projects/label/en/latest/installation.html#windows)

### GPU Acceleration (Optional Dependencies)
Following are the optional dependencies which can help you to accelerate some GPU based transforms from MONAI. These dependencies are enabled by default if you are using `projectmonai/monailabel` docker.
- [CUCIM](https://pypi.org/project/cucim/)
- [CUPY](https://docs.cupy.dev/en/stable/install.html#installing-cupy)
- [CUDA Toolkit](https://developer.nvidia.com/cuda-downloads)

### Development version

To install the _**latest features**_ using one of the following options:

<details>
  <summary><strong>Git Checkout (developer mode)</strong></summary>
  <a href="https://github.com/Project-MONAI/MONAILabel"><img alt="GitHub tag (latest SemVer)" src="https://img.shields.io/github/v/tag/Project-MONAI/monailabel"></a>
  <br>
  <pre>
  git clone https://github.com/Project-MONAI/MONAILabel
  pip install -r MONAILabel/requirements.txt
  export PATH=$PATH:`pwd`/MONAILabel/monailabel/scripts</pre>
  <p>If you are using DICOM-Web + OHIF then you have to build OHIF package separate.  Please refer [here](https://github.com/Project-MONAI/MONAILabel/tree/main/plugins/ohif#development-setup).</p>
</details>

<details>
  <summary><strong>Weekly Release</strong></summary>
  <a href="https://badge.fury.io/py/monailabel-weekly"><img src="https://badge.fury.io/py/monailabel-weekly.svg" alt="PyPI version" height="18"></a>
  <br>
  <pre>pip install monailabel-weekly -U</pre>
</details>

<details>
  <summary><strong>Docker</strong></summary>
  <img alt="Docker Image Version (latest semver)" src="https://img.shields.io/docker/v/projectmonai/monailabel">
  <br>
  <pre>docker run --gpus all --rm -ti --ipc=host --net=host projectmonai/monailabel:latest bash</pre>
</details>

## MONAI Label Sample Applications
<table>
  <tr></tr>
  <tr>
    <td colspan="2">
      <h3><big>Radiology</big></h3>
    </td>
  </tr>
  <tr>
    <th>Overview</th>
    <th>Models</th>
  </tr>
  <tr></tr>  
  <tr>
    <td>
      <h3>Labeling App for Radiography Imaging</h3>
      <p>This app has example models to do both interactive and automated segmentation over radiology (3D) images. Including auto segmentation with the latest deep learning models (e.g., UNet, UNETR) for multiple abdominal organs. Interactive tools include DeepEdit and Deepgrow for actively improving trained models and deployment.</p>
      <a href="">Explore Radiology Applications</a>
    </td>
    <td>
      <ul>
        <li>Deepedit</li>
        <li>Deepgrow</li>
        <li>Segmentation</li>
        <li>Spleen Segmentation</li>
        <li>Multi-Stage Vertebra Segmentation</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <h3><big>Pathology</big></h3>
    </td>
  </tr>
  <tr>
    <th>Overview</th>
    <th>Models</th>
  </tr>
  <tr></tr>
  <tr>
    <td>
      <h3>Labeling App for Microscopy Imaging</h3>
      <p>This app has example models to do both interactive and automated segmentation over pathology (WSI) images. Including nuclei multi-label segmentation for Neoplastic cells, Inflammatory, Connective/Soft tissue cells, Dead Cells, and Epithelial. The app provides interactive tools including DeepEdits for interactive nuclei segmentation.</p>
      <a href="">Explore Pathology Applications</a>      
    </td>
    <td>
      <ul>
        <li>Deepedit</li>
        <li>Deepgrow</li>
        <li>Segmentation</li>
        <li>Spleen Segmentation</li>
        <li>Multi-Stage Vertebra Segmentation</li>
      </ul>
    </td>    
  </tr>
  <tr>
    <td colspan="2">
      <h3><big>Video</big></h3>
    </td>
  </tr>
  <tr>
    <th>Overview</th>
    <th>Models</th>
  </tr>
<tr></tr>  
  <tr>
    <td>
      <h3>Labeling App for Video</h3>
      <p>The Endoscopy app enables users to use interactive, automated segmentation and classification models over 2D images for endoscopy usecase. Combined with CVAT, it will demonstrate the fully automated Active Learning workflow to train + fine-tune a model.</p>
      <a href="">Explore Video Applications</a>      
    </td>
    <td>
      <ul>
        <li>Deepedit</li>
        <li>Deepgrow</li>
        <li>Segmentation</li>
        <li>Spleen Segmentation</li>
        <li>Multi-Stage Vertebra Segmentation</li>
      </ul>
    </td>    
  </tr>
  <tr>
    <td colspan="2">
      <h3><big>Bundles</big></h3>
    </td>
  </tr>
  <tr>
    <th>Overview</th>
    <th>Models</th>
  </tr>
  <tr></tr>  
  <tr>
    <td>
      <h3>Flexible Labeling with Customized Models</h3>
      <p>The Bundle app enables users with customized models for inference, training or pre and post processing any target anatomies. The specification for MONAILabel integration of the Bundle app links archived Model-Zoo for customized labeling (e.g., the third-party transformer model for labeling renal cortex, medulla, and pelvicalyceal system. Interactive tools such as DeepEdits).</p>
      <a href="">Explore MONAI Bundles</a>      
    </td>
    <td>
      <ul>
        <li>Deepedit</li>
        <li>Deepgrow</li>
        <li>Segmentation</li>
        <li>Spleen Segmentation</li>
        <li>Multi-Stage Vertebra Segmentation</li>
      </ul>
    </td>    
  </tr>
</table>

## MONAI Label Supported Viewers
<table>
  <tr></tr>
  <tr>
    <td colspan="2">
      <h3><big>Radiology</big></h3>
    </td>
  </tr>
  <tr>
    <th>Viewer</th>
    <th>Screenshot</th>
  </tr>
  <tr></tr>  
  <tr>
    <td>
      <h3>3D Slicer</h3>
      <p>3D Slicer, a free and open-source platform for analyzing, visualizing and understanding medical image data. In MONAI Label, 3D Slicer is most tested with radiology studies and algorithms, develpoment and integration.</p>
      <a href="">Install 3D Slicer and MONAI Plugin</a>
    </td>
    <td>
      <ul>
        <li>Deepedit</li>
        <li>Deepgrow</li>
        <li>Segmentation</li>
        <li>Spleen Segmentation</li>
        <li>Multi-Stage Vertebra Segmentation</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td colspan="2">
      <h3><big>Pathology</big></h3>
    </td>
  </tr>
  <tr>
    <th>Overview</th>
    <th>Screenshot</th>
  </tr>
  <tr></tr>
  <tr>
    <td>
      <h3>Labeling App for Microscopy Imaging</h3>
      <p>This app has example models to do both interactive and automated segmentation over pathology (WSI) images. Including nuclei multi-label segmentation for Neoplastic cells, Inflammatory, Connective/Soft tissue cells, Dead Cells, and Epithelial. The app provides interactive tools including DeepEdits for interactive nuclei segmentation.</p>
      <a href="">Explore Pathology Applications</a>      
    </td>
    <td>
      <ul>
        <li>Deepedit</li>
        <li>Deepgrow</li>
        <li>Segmentation</li>
        <li>Spleen Segmentation</li>
        <li>Multi-Stage Vertebra Segmentation</li>
      </ul>
    </td>    
  </tr>
  <tr>
    <td colspan="2">
      <h3><big>Video</big></h3>
    </td>
  </tr>
  <tr>
    <th>Overview</th>
    <th>Screenshot</th>
  </tr>
<tr></tr>  
  <tr>
    <td>
      <h3>Labeling App for Video</h3>
      <p>The Endoscopy app enables users to use interactive, automated segmentation and classification models over 2D images for endoscopy usecase. Combined with CVAT, it will demonstrate the fully automated Active Learning workflow to train + fine-tune a model.</p>
      <a href="">Explore Video Applications</a>      
    </td>
    <td>
      <ul>
        <li>Deepedit</li>
        <li>Deepgrow</li>
        <li>Segmentation</li>
        <li>Spleen Segmentation</li>
        <li>Multi-Stage Vertebra Segmentation</li>
      </ul>
    </td>    
  </tr>
</table>




## Visualization Tools

MONAI Label supports the most adopted open-source viewers for Radiology,  Pathology, and Endoscopy images.

### 3D Slicer

3D Slicer, a free and open-source platform for analyzing, visualizing and understanding medical image data. In MONAI Label, 3D Slicer is most tested with radiology studies and
algorithms, develpoment and integration.

MONAI Label is most currently tested and supported with stable release of 3D Slicer every version. Preview version of 3D Slicer is not fully tested and supported.

To install stable released version of 3D Slicer, see [3D Slicer installation](https://download.slicer.org/).
Currently, Windows and Linux version are supported.

### OHIF (Web-based)

The Open Health Imaging Foundation (OHIF) Viewer is an open source, web-based, medical imaging platform.
It aims to provide a core framework for building complex imaging applications.

At this point OHIF can be used to annotate the data in the DICOM server via the MONAI Label server.
To use OHIF web-based application, refer to [extensible web imaging platform](https://ohif.org/)

### QuPath

Quantitative Pathology & Bioimage Analysis (QuPath) is an open, powerful, flexible, extensible software platform for bioimage analysis.

To install stable released version of QuPath, see [QuPath installation](https://qupath.github.io/).
Currently, Windows and Linux version are supported. Detailed documentation can be found [QuPath Doc](https://qupath.readthedocs.io/en/stable/).


### CVAT

CVAT is an interactive video and image annotation tool for computer vision.

To install stable released version of CVAT, see [CVAT installation](https://github.com/opencv/cvat).
Currently, Windows and Linux version are supported. Detailed documentation can be found [CVAT Doc](https://opencv.github.io/cvat/docs/).


## Plugins

### [3D Slicer](https://download.slicer.org/) (radiology)

Download and install 3D Slicer with the [installation page](https://docs.monai.io/projects/label/en/latest/installation.html).
Install MONAI Label plugin from Slicer Extension Manager.

Refer [3D Slicer plugin](https://github.com/Project-MONAI/MONAILabel/tree/main/plugins/slicer) for other options to
install and run MONAI Label plugin in 3D Slicer.
> To avoid accidentally using an older Slicer version, you may want to _uninstall_ any previously installed 3D Slicer
> package.

### [OHIF](https://ohif.org/) (radiology)

MONAI Label comes with [pre-built plugin](https://github.com/Project-MONAI/MONAILabel/tree/main/plugins/ohif)
for [OHIF Viewer](https://github.com/OHIF/Viewers). To use OHIF
Viewer, you need to provide **DICOMWeb** instead of FileSystem as _studies_ when you start the server.
> Please install [Orthanc](https://www.orthanc-server.com/download.php) before using OHIF Viewer.
> For Ubuntu 20.x, Orthanc can be installed as `apt-get install orthanc orthanc-dicomweb`. However, you have to
> **upgrade to latest version** by following steps
> mentioned [here](https://book.orthanc-server.com/users/debian-packages.html#replacing-the-package-from-the-service-by-the-lsb-binaries).
>
> You can use [PlastiMatch](https://plastimatch.org/plastimatch.html#plastimatch-convert) to convert NIFTI to DICOM

```bash
  # start server using DICOMWeb
  monailabel start_server --app apps/radiology --studies http://127.0.0.1:8042/dicom-web

  # to disable DICOM to NIFTI conversion for faster performance
  export MONAI_LABEL_DICOMWEB_CONVERT_TO_NIFTI=false
  monailabel start_server --app apps/radiology --studies http://127.0.0.1:8042/dicom-web
```
> NOTE:: 3D-Slicer is not supported without DICOM to NIFTI conversion
>
> OHIF Viewer will be accessible at http://127.0.0.1:8000/ohif/

![OHIF](https://raw.githubusercontent.com/Project-MONAI/MONAILabel/main/docs/images/ohif.png)

> **NOTE:** OHIF does not yet support Multi-Label interaction for DeepEdit.  And you can still use 3D Slicer when MONAILabel is connected to DICOMWeb.

### [QuPath](https://qupath.github.io/) (pathology)

You can download sample whole slide images
from [https://portal.gdc.cancer.gov/repository](https://portal.gdc.cancer.gov/repository?filters=%7B%22op%22%3A%22and%22%2C%22content%22%3A%5B%7B%22op%22%3A%22in%22%2C%22content%22%3A%7B%22field%22%3A%22files.data_type%22%2C%22value%22%3A%5B%22Slide%20Image%22%5D%7D%7D%5D%7D)

```bash
  # start server using pathology over downloaded whole slide images
  monailabel start_server --app apps/pathology --studies wsi_images
```

Refer [QuPath](plugins/qupath) for installing and running MONAILabel plugin in QuPath.

![image](https://raw.githubusercontent.com/Project-MONAI/MONAILabel/main/docs/images/qupath.jpg)

### [Digital Slide Archive (DSA)](https://digitalslidearchive.github.io/digital_slide_archive/) (pathology)

Refer [Pathology](sample-apps/pathology) for running a sample pathology use-case in MONAILabel.
> **NOTE:** The *DSA Plugin* is under *active development*.

![image](https://raw.githubusercontent.com/Project-MONAI/MONAILabel/main/docs/images/dsa.jpg)

### [CVAT](plugins/cvat)

Install [CVAT](https://opencv.github.io/cvat/docs/administration/basics/installation/) and
enable [Semi-Automatic and Automatic Annotation](https://opencv.github.io/cvat/docs/administration/advanced/installation_automatic_annotation/).
Refer [CVAT Instructions](https://github.com/Project-MONAI/MONAILabel/tree/main/plugins/cvat) for deploying available MONAILabel
pathology/endoscopy models into CVAT.

<table>
<tr>
<td><img src="https://raw.githubusercontent.com/Project-MONAI/MONAILabel/main/docs/images/cvat_detector.jpeg" width="300"/></td>
<td><img src="https://raw.githubusercontent.com/Project-MONAI/MONAILabel/main/docs/images/cvat_active_learning.jpeg" width="300"/></td>
</tr>
</table>

## Cite

If you are using MONAI Label in your research, please use the following citation:

```bash
@article{DiazPinto2022monailabel,
   author = {Diaz-Pinto, Andres and Alle, Sachidanand and Ihsani, Alvin and Asad, Muhammad and
            Nath, Vishwesh and P{\'e}rez-Garc{\'\i}a, Fernando and Mehta, Pritesh and
            Li, Wenqi and Roth, Holger R. and Vercauteren, Tom and Xu, Daguang and
            Dogra, Prerna and Ourselin, Sebastien and Feng, Andrew and Cardoso, M. Jorge},
    title = {{MONAI Label: A framework for AI-assisted Interactive Labeling of 3D Medical Images}},
  journal = {arXiv e-prints},
     year = 2022,
     url  = {https://arxiv.org/pdf/2203.12362.pdf}
}

@inproceedings{DiazPinto2022DeepEdit,
      title={{DeepEdit: Deep Editable Learning for Interactive Segmentation of 3D Medical Images}},
      author={Diaz-Pinto, Andres and Mehta, Pritesh and Alle, Sachidanand and Asad, Muhammad and Brown, Richard and Nath, Vishwesh and Ihsani, Alvin and Antonelli, Michela and Palkovics, Daniel and Pinter, Csaba and others},
      booktitle={MICCAI Workshop on Data Augmentation, Labelling, and Imperfections},
      pages={11--21},
      year={2022},
      organization={Springer}
}
 ```

Optional Citation: if you are using active learning functionality from MONAI Label, please support us:

```bash
@article{nath2020diminishing,
  title={Diminishing uncertainty within the training pool: Active learning for medical image segmentation},
  author={Nath, Vishwesh and Yang, Dong and Landman, Bennett A and Xu, Daguang and Roth, Holger R},
  journal={IEEE Transactions on Medical Imaging},
  volume={40},
  number={10},
  pages={2534--2547},
  year={2020},
  publisher={IEEE}
}
```

## Contributing

For guidance on making a contribution to MONAI Label, see
the [contributing guidelines](https://github.com/Project-MONAI/MONAILabel/blob/main/CONTRIBUTING.md).

## Community

Join the conversation on Twitter [@ProjectMONAI](https://twitter.com/ProjectMONAI) or join
our [Slack channel](https://projectmonai.slack.com/archives/C031QRE0M1C).

Ask and answer questions over
on [MONAI Label's GitHub Discussions tab](https://github.com/Project-MONAI/MONAILabel/discussions).

## Links

- Website: https://monai.io/
- API documentation: https://docs.monai.io/projects/label
- Code: https://github.com/Project-MONAI/MONAILabel
- Project tracker: https://github.com/Project-MONAI/MONAILabel/projects
- Issue tracker: https://github.com/Project-MONAI/MONAILabel/issues
- Wiki: https://github.com/Project-MONAI/MONAILabel/wiki
- Test status: https://github.com/Project-MONAI/MONAILabel/actions
- PyPI package: https://pypi.org/project/monailabel/
- Weekly previews: https://pypi.org/project/monailabel-weekly/
- Docker Hub: https://hub.docker.com/r/projectmonai/monailabel
- Client API: https://www.youtube.com/watch?v=mPMYJyzSmyo
- Demo Videos: https://www.youtube.com/c/ProjectMONAI
