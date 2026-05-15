# SmartWaste Analyzer - AI-Powered Waste Detection & Contamination Assessment

A comprehensive computer vision pipeline for real-time waste detection, contamination analysis, and environmental-economic valuation using YOLOv8 and custom CNN models.

## Overview

**SmartWaste Analyzer** is an end-to-end system that:
1. Detects waste items in images/videos using YOLOv8 (12 waste classes)
2. Analyzes contamination levels with a custom CNN (0-100% contamination score)
3. Calculates economic value (₹) and CO₂ environmental impact saved

### Key Features
- **Module 1:** YOLOv8 Nano for real-time waste detection (12 classes)
- **Module 2:** Custom CNN for contamination level assessment  
- **Module 3:** Dual valuation engine (economic + environmental impact)
- **Dataset:** 15,150 images from Garbage Classification Dataset (Kaggle)
- **Real-time Processing:** Optimized for edge computing and live inference

## Project Structure

```
SmartWaste-Analyzer/
├── Code/
│   └── main_code.ipynb          # Main implementation (Jupyter notebook)
├── Dataset/
│   └── archive.zip              # Training dataset (download separately)
├── output images/
│   ├── evaluation/              # Model evaluation metrics
│   ├── graphs/                  # Training graphs & visualizations
│   ├── models/                  # Trained model weights
│   │   ├── contamination_cnn_best.h5
│   │   ├── contamination_cnn_final.h5
│   │   └── yolov8_waste_best.pt
│   └── results/                 # Inference results
├── report/
│   └── Smart Waste Analyzer(final report).pdf
├── research/                    # Related research papers & notes
└── requirements.txt             # Python dependencies
```

## Installation

### Prerequisites
- Python 3.8+
- pip or conda
- GPU (optional, for faster training)

### Setup Instructions

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/SmartWaste-Analyzer.git
cd SmartWaste-Analyzer
```

2. **Create virtual environment**
```bash
# Using venv
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate

# OR using conda
conda create -n smartwaste python=3.9
conda activate smartwaste
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Download dataset** (Optional)
   - Download from [Kaggle Garbage Classification Dataset](https://www.kaggle.com/datasets/mostafaabla/garbage-classification)
   - Extract to `Dataset/` folder

## Usage

> Note: `Dataset/`, `output images/`, and model weights are not included in the GitHub repository by default. Download the dataset separately and use the notebook to generate local outputs or place model weights into `output images/models/`.

### Running in Jupyter Notebook (Recommended)

```bash
jupyter notebook Code/main_code.ipynb
```

Follow the cells sequentially:
1. Install dependencies
2. Load and explore dataset
3. Train YOLOv8 waste detector
4. Train contamination CNN
5. Run inference on test images
6. Generate valuation report

### Key Parameters

**YOLOv8 Training:**
- Model: YOLOv8n (Nano)
- Epochs: 50
- Batch Size: 16
- Image Size: 640x640

**Contamination CNN:**
- Architecture: Custom 4-layer CNN
- Input Size: 128x128
- Output: Contamination percentage (0-100)

## Model Architecture

### Module 1: YOLOv8 Nano
- Lightweight YOLO variant for real-time detection
- 12 waste classes: plastic, paper, metal, glass, food, cardboard, etc.
- mAP50: ~85% on test set

### Module 2: Contamination CNN
- Custom CNN with 4 convolutional layers
- Dropout layers for regularization
- Outputs continuous contamination score
- Accuracy: ~92% on validation set

### Module 3: Valuation Engine
- Economic valuation based on waste type
- CO₂ impact calculation
- Combined score dashboard

## Results & Metrics

- YOLOv8 Detection mAP: 0.85
- Contamination CNN Accuracy: 0.92
- Real-time inference: ~30 FPS on GPU
- Dataset: 15,150 images across 12 classes

See `report/` and `output images/` for detailed results, graphs, and visualizations.

## Technologies Used

- **Deep Learning:** TensorFlow, Keras, PyTorch
- **Computer Vision:** YOLOv8, OpenCV
- **Data Processing:** NumPy, Pandas, Scikit-learn
- **Visualization:** Matplotlib, Seaborn
- **Framework:** Jupyter Notebook

## Dataset Information

- **Source:** [Kaggle - Garbage Classification Dataset](https://www.kaggle.com/datasets/mostafaabla/garbage-classification)
- **Total Images:** 15,150
- **Classes:** 12 waste types
- **Train/Val/Test Split:** 70/15/15

## Future Enhancements

- Real-time video stream processing
- Mobile app deployment (TFLite)
- Multi-camera support for industrial recycling plants
- Advanced contamination detection (liquid, hazardous materials)
- Integration with IoT devices for automated waste sorting
- Real-time dashboard and analytics platform

## Model Weights

Pre-trained model weights are referenced in `output images/models/`, but they are excluded from the GitHub repository. To use the project, either train the models locally or place downloaded weights into `output images/models/`.
- `contamination_cnn_best.h5` - Best contamination model
- `yolov8_waste_best.pt` - Best YOLOv8 detector

## Citation

If you use this project in research, please cite:
```bibtex
@misc{smartwaste2024,
  title={SmartWaste Analyzer: AI-Powered Waste Detection and Contamination Assessment},
  author={Your Name},
  year={2024}
}
```

## License

This project is licensed under the MIT License - see [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Support

For issues, questions, or suggestions:
- Create an issue on GitHub
- Contact: your.email@example.com

## Acknowledgments

- Kaggle for the Garbage Classification Dataset
- Ultralytics for YOLOv8 framework
- TensorFlow/Keras communities
- All contributors and researchers in computer vision

---

**Project Status:** Complete  
**Last Updated:** May 2024  
**Version:** 1.0
