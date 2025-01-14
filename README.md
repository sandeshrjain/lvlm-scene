# lvlm-scene
Dataset- Semantic Understanding of Traffic Scenes with Large Vision Language Models

## README for Dataset Release

### Dataset Overview
Our dataset is designed to facilitate research and evaluation in autonomous vehicle perception, focusing on transportation safety-critical questions and scene understanding. The dataset is compiled from open-source datasets, primarily utilizing the KITTI and NuScenes datasets, renowned for their comprehensive perception data for autonomous vehicles.

### Dataset Contents
The dataset comprises the following components:

1. **Perception Data Sources**:
   - **KITTI Dataset**: We utilized the KITTI 3D Multi-object Tracking set (all training and testing videos), which includes LiDAR-based point clouds, front camera images, IMU/GPS data, and calibration files. This dataset offers a sequential data structure that facilitates scene description and kinematic analysis.
   - **NuScenes Dataset**: We also incorporated data from the NuScenes dataset, including lidar-based point clouds, camera images, and calibration information. The dataset encompasses urban environments with dense traffic, pedestrians, cyclists, and varied work-zone interactions (Front Camera Videos From V1.0 Training Set: video_1542800867362460_1542800988012460, video_1542800387762460_1542800848012460, video_1538984253362460_1542800368012460, video_1538448763912460_1538984233612474, video_1535489315862404_1535657108362404, video_1535385111862404_1535489296112404, video_1532402946662460_1538448744512460).

2. **MCQ-based Safety-critical Questions and Annotations**:
   - To augment the existing annotations focused on localization tasks, we developed a collection of 40 sets of multiple-choice questions (MCQs). These questions assess perception abilities and interpretation accuracy of Large-scale Vision and Language Models (LVLMs) across various transportation safety aspects.
   - The MCQs are categorized into five key aspects:
     - Road Infrastructure (RI)
     - Vulnerable Road Users (VRU)
     - Human Factors and Driver Behavior (HF)
     - Vehicle-Vehicle Interactions (V2VI)
     - Other Environmental Factors (OEF)
   - A team of human annotators meticulously annotated the dataset, resulting in 2,400 unique question-scene pairs.
   - Annotated responses for the training are saved under the [megajson](./megajson.json) file for the KITTI dataset and [nusc_megajson](./nusc_megajson.json) for the NuScenes set.
3. **Component-wise Descriptive Scene Understanding**:
   - In addition to MCQs, we introduced open-ended questions aligned with the five key aspects. These questions enable a more nuanced assessment of LVLMs' scene understanding capabilities.
   - Traffic safety experts evaluate model-generated responses based on completeness, relevance, and correctness for each aspect, providing qualitative insights into model performance.
   - Sample responses are provided under the [descriptions_train_megajson](./descriptions_train_megajson.json) file.

### Dataset Structure
The dataset is organized into:
- **Video Data**: Includes sequences from KITTI and NuScenes datasets.
- **Annotations**: Annotated with MCQs and open-ended questions aligned with transportation safety aspects.
- **Evaluation Metrics**: Detailed performance metrics for evaluating LVLMs' performance on transportation-related aspects.

### Dataset Usage
Researchers and practitioners can leverage this dataset to:
- Evaluate LVLMs' ability to understand transportation scenes.
- Benchmark and compare model performance across safety-critical aspects.
- Develop and validate perception algorithms for autonomous vehicles.

### Benchmarking Results

#### Aspect-based Performance

| Dataset | Models      | Modality | Road Infrastructure (RI) | Vulnerable Road Users (VRU) | Human Factors & Driver Behavior (HF) | Vehicle-Vehicle Interactions (V2VI) | Other Environmental Factors (OEF) |
|---------|-------------|----------|--------------------------|------------------------------|--------------------------------------|------------------------------------|-----------------------------------|
| KITTI   | Video-LLaVA | Visual   | 66.07                    | 60.00                        | 81.11                                | 80.83                              | 95.00                             |
| KITTI   | GPT-4       | Visual   | 81.56                    | 80.43                        | 85.60                                | 77.78                              | 87.11                             |
| KITTI   | GPT-4       | Visual + 3D Detection | 76.63   | 71.53                        | 89.32                                | 81.25                              | 80.65                             |
| NuScenes| Video-LLaVA | Visual   | 58.62                    | 56.80                        | 71.24                                | 76.56                              | 90.50                             |
| NuScenes| GPT-4       | Visual   | 78.60                    | 85.19                        | 81.48                                | 85.17                              | 87.83                             |

#### Overall Performance

| Dataset | Models      | Modality | Overall Performance |
|---------|-------------|----------|---------------------|
| KITTI   | Video-LLaVA | Visual   | 74.09               |
| KITTI   | GPT-4       | Visual   | 81.75               |
| KITTI   | GPT-4       | Visual + 3D Detection | 79.69 |
| NuScenes| Video-LLaVA | Visual   | 66.94               |
| NuScenes| GPT-4       | Visual   | 81.39               |

### Citation
If you find the work helpful, please consider citing.

```bibtex
@INPROCEEDINGS{10588373,
  author={Jain, Sandesh and Thapa, Surendrabikram and Chen, Kuan-Ting and Abbott, A. Lynn and Sarkar, Abhijit},
  booktitle={2024 IEEE Intelligent Vehicles Symposium (IV)}, 
  title={Semantic Understanding of Traffic Scenes with Large Vision Language Models}, 
  year={2024},
  pages={1580-1587},
  keywords={Location awareness;Visualization;Laser radar;Semantics;Transportation;Cameras;Cognition;large vision language models (LVLM);scene analysis;automated perception},
  doi={10.1109/IV55156.2024.10588373}
}
