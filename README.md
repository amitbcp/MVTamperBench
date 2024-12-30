# MVTamperBench

## Overview

MVTamperBench is a comprehensive benchmark designed to evaluate the robustness of Vision-Language Models (VLMs) against adversarial video tampering effects. The benchmark includes five tampering types:

1. **Frame Dropping**: Frames are removed to simulate missing content.
2. **Masking**: Frames are obscured with a black mask to simulate concealment.
3. **Repetition**: Frames are repeated to mimic redundancy.
4. **Rotation**: Frames are rotated to test spatial manipulation.
5. **Substitution**: Frames are replaced with frames from another video to simulate content substitution.

The below image shows how the tampering effects work in a video.
![Tampered Frames](https://github.com/amitbcp/TamperBench/blob/main/Images/Tampering_Frames_cut.png "Frame Comparison of Tampering Effects")

This benchmark facilitates robust evaluations using state-of-the-art models across diverse tampering effects, enabling the development of tamper-resilient video understanding systems.

---

## Dataset

The dataset for MVTamperBench is derived from the MVBench collection. It includes videos that are systematically tampered to test the robustness of models against adversarial effects.

### Download Dataset
You can download the dataset from the following link:
[Download MVTamperBench Dataset](https://huggingface.co/datasets/Srikant86/MVTamperBench/tree/main/video)

### Dataset Structure

The dataset is structured as follows:
```
MVBench-Dataset/
│
├── Videos/
│   ├── Original/
│   ├── Tampered/
│
└── Metadata/
    ├── original_metadata.csv
    ├── tampered_metadata.csv
```

---

## Key Features

- **Extensive Evaluation**: Benchmarked against 20 state-of-the-art models, including multimodal architectures.
- **Five Tampering Effects**: Frame dropping, masking, repetition, rotation, and substitution.
- **Diverse Metrics**: Evaluation based on accuracy, robustness coefficient, and latency.
- **Reproducibility**: Experiments conducted on NVIDIA A100 GPUs with standard preprocessing pipelines.
- **Open-Source Integration**: Modular codebase compatible with VLMEvalKit.

---

## Experimentation and Results

### Experimental Setup

- **Models**: 20 state-of-the-art models, including molmo variants, InternVL2 variants, and Llama-3-VILA models.
- **Evaluation Metrics**:
  - *Accuracy*: Correctly identified tampering effects.
  - *Robustness Coefficient*: Stability across tampering types.![Distribution image](https://github.com/amitbcp/TamperBench/blob/main/Images/Distribution%20image.png "Tampered Video Length Distribution")

  - *Latency*: Computational efficiency.
- **Environment**: Experiments conducted on NVIDIA A100 GPUs.

### Results Highlights

- **High-Performing Models**: molmo-7B-D-0924 and molmoE-1B-0924 achieved 100% accuracy across all tampering effects.
- **Challenging Effects**: Frame dropping was the most difficult for weaker models.

---

### Visualizations

#### Overall Model Performance
![Overall Model Performance](https://github.com/amitbcp/TamperBench/blob/main/Images/OverallPerformancebar.jpg "Overall Model Performance showcases the robustness og the models towards the tampering effects")

#### Heatmap of Model Performance
![Heatmap of Model Performance](https://github.com/amitbcp/TamperBench/blob/main/Images/Heatmap_of_Effects.jpg "Heatmap showing model robustness across tampering types")

#### Radar Chart of Robustness
![Radarchart of Model Performance](https://github.com/amitbcp/TamperBench/blob/main/Images/effects_on_models_radar_chart_from_dataframe.png "Radar Chart showing Models perfromance")

### Bar Chart for Visualizing the models performance across the Tampering Effects
![Bar Chart of Model Performance](https://github.com/amitbcp/TamperBench/blob/main/Images/model_performance_chart_from_dataframe.jpg "Model Performance on each Tampering Effects")


---

## Future Directions

1. **Incorporating Newer Models**: Ensure benchmark remains up-to-date with the latest models.
2. **Expanding Tampering Types**: Add manipulations like noise injection and partial masking.
3. **Localized Vulnerability Analysis**: Assess tampering in specific video segments.
4. **Domain-Specific Evaluation**: Apply in domains like medical imaging, surveillance, and entertainment.
5. **Adversarial Training**: Enhance model generalization using adversarially manipulated scenarios.

---

## How to Use

1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/mvtamperbench.git
   cd mvtamperbench
   ```


2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the benchmark:
   ```bash
   python run_benchmark.py --dataset <path_to_dataset> --output <output_directory>
   ```


## Citation
If you use MVTamperBench in your research, please cite:
```bibtex
@misc{agarwal2024mvtamperbenchevaluatingrobustnessvisionlanguage,
      title={MVTamperBench: Evaluating Robustness of Vision-Language Models}, 
      author={Amit Agarwal and Srikant Panda and Angeline Charles and Bhargava Kumar and Hitesh Patel and Priyanranjan Pattnayak and Taki Hasan Rafi and Tejaswini Kumar and Dong-Kyu Chae},
      year={2024},
      eprint={2412.19794},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2412.19794}, 
}
```

---

## License
MVTamperBench is released under the MIT License. See `LICENSE` for more details.
