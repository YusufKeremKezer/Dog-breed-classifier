An image classification project that uses pre-trained CNN models (AlexNet, ResNet, VGG) to identify dog breeds and distinguish between dogs, cats, and other animals. Part of Udacity's **AI Programming with Python** Nanodegree.

## Overview

This project implements a complete image classifier pipeline that:
- Processes pet images using command-line arguments
- Classifies images using three different CNN architectures
- Compares classifier predictions against ground truth labels
- Evaluates model performance on dog breed identification

## Key Features

- **Multi-model comparison**: AlexNet, ResNet, and VGG architectures
- **Dog vs Non-dog detection**: Distinguishes dogs from other animals
- **Breed identification**: Identifies specific dog breeds
- **Performance statistics**: Comprehensive accuracy metrics

## Project Structure

```
├── get_input_args.py      # Command line argument parser
├── get_pet_labels.py      # Creates ground truth labels from filenames
├── classifier.py          # Runs pre-trained CNN models
├── classify_images.py     # Classifies images using selected architecture
├── adjust_results4_isadog.py  # Adjusts results for dog/non-dog classification
├── calculates_results_stats.py  # Calculates performance statistics
├── print_results.py       # Displays formatted results
└── check_images.py        # Main entry point
```

## Usage

### Run with specific model:
```bash
python check_images.py --dir pet_images/ --arch alexnet --dogfile dognames.txt
```

### Run all models (batch):
```bash
sh run_models_batch.sh
```

**Arguments:**
- `--dir`: Path to folder containing images
- `--arch`: Model architecture (`alexnet`, `resnet`, or `vgg`)
- `--dogfile`: File containing list of valid dog names

## Experimental Results

### Performance Comparison (40 images: 30 dogs, 10 non-dogs)

| Model   | Runtime | Dog Accuracy | Non-Dog Accuracy | Breed Accuracy | Match Rate |
|---------|---------|--------------|------------------|----------------|------------|
| AlexNet | 17s     | 100%         | 100%             | 80.0%          | 75.0%      |
| ResNet  | 48s     | 100%         | 90%              | 90.0%          | -          |
| VGG     | 89s     | 100%         | 100%             | 93.3%          | 87.5%      |

### Key Findings

1. **VGG** achieved the highest breed classification accuracy (93.3%) but was the slowest (89s)
2. **AlexNet** was the fastest (17s) with acceptable accuracy (80% breed)
3. **ResNet** offered a middle ground with 90% breed accuracy and 48s runtime
4. All models achieved 100% accuracy on dog detection

### Uploaded Images Test

All three models successfully:
- Classified dog images consistently across architectures
- Correctly identified non-dog images (cats, objects)

**Recommended Model**: AlexNet for time-sensitive applications; VGG for maximum accuracy.

## Output Files

- `*_pet-images.txt`: Detailed results for each model architecture
- `check_images.txt`: Analysis of uploaded image classifications

## Install Requirements

- pip install -r requirements.txt


## License

Part of Udacity's AI Programming with Python Nanodegree curriculum.
