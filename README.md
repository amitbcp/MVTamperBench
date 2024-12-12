# MVTamperBench

## Overview

MVTamperBench is a comprehensive benchmark designed to evaluate the robustness of Vision-Language Models (VLMs) against adversarial video tampering effects. The benchmark includes five tampering types:

1. **Frame Dropping**: Frames are removed to simulate missing content.
2. **Masking**: Frames are obscured with a black mask to simulate concealment.
3. **Repetition**: Frames are repeated to mimic redundancy.
4. **Rotation**: Frames are rotated to test spatial manipulation.
5. **Substitution**: Frames are replaced with frames from another video to simulate content substitution.

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
  - *Robustness Coefficient*: Stability across tampering types.![Distribution image]()

  - *Latency*: Computational efficiency.
- **Environment**: Experiments conducted on NVIDIA A100 GPUs.

### Results Highlights

- **High-Performing Models**: molmo-7B-D-0924 and molmoE-1B-0924 achieved 100% accuracy across all tampering effects.
- **Challenging Effects**: Frame dropping was the most difficult for weaker models.

---

### Visualizations
#### Heatmap of Model Performance
![Heatmap of Model Performance](.png "Heatmap showing model robustness across tampering types")

#### Radar Chart of Robustness
![Radarchart of Model Performance](.png "Heatmap showing model robustness across tampering types")
(Add space for heatmaps, radar charts, and bar charts of model performance.)

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
![Distribution image](https://github.com/user-attachments/assets/16ea4eac-3b67-4816-942f-48776799d8aa)

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
@article{mvtamperbench2024,
  title={MVTamperBench: A Benchmark for Robustness Against Video Tampering Effects},
  author={Your Name and Collaborators},
  journal={Journal of Video Understanding},
  year={2024}
}
```

---

## License
MVTamperBench is released under the MIT License. See `LICENSE` for more details.
