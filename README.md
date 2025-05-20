# DA6401_Assignment3

# Marathi-English Transliteration Models

This repository includes two distinct methods for implementing Sequence-to-Sequence (Seq2Seq) models for Marathi-English transliteration using the Dakshina dataset:

## Project Structure

```
DA6401_Assignment3/
├── With_attention/
│   ├── dla3-attention.ipynb     # Jupyter notebook with attention implementation
│   ├── prediction_attention.csv  # Prediction results from attention model
│   └── heatmap,connection grid             # Visualization images (2 files)
├── Without_attention/
│   ├── dla3-without-attention.ipynb       # Jupyter notebook with vanilla implementation
│   ├── prediction_vanilla.csv    # Prediction results from vanilla model
│   └── sample                    # Visualization image (1 file)
└── README.md                     # Main README file
```

## Summary

 In this project, two transliteration strategies are used and contrasted:

 1. Using recurrent neural networks (RNN/GRU/LSTM), the standard encoder-decoder architecture known as **Vanilla Seq2Seq** encodes the source sequence into a fixed-length vector and decodes it into the target sequence.

 2. **Attention-based Seq2Seq** is improved architecture overcomes the drawbacks of compressing all information into a fixed-length vector by enabling the decoder to concentrate on distinct segments of the input sequence at each decoding step.


## Key Features

- **Multiple RNN Cell Types**: Support for RNN, GRU, and LSTM cells
- **Beam Search Decoding**: Enhanced decoding strategy for improved output quality
- **Attention Mechanism**: Visual attention to focus on relevant input characters
- **Visualization**: Attention weight visualization to understand model behavior

## Data

This project uses the Dakshina dataset for Hindi-English transliteration. The dataset can be downloaded from the [official source](https://github.com/google-research-datasets/dakshina).

## Comparison of Models

| Model | Test Accuracy | Benefits |
|-------|---------------|----------|
| Vanilla Seq2Seq | ~55% | Simpler architecture, fewer parameters |
| Attention Seq2Seq | ~60% | Better handling of long sequences, improved accuracy |

## Setup and Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/Rajat26402/DA6401_Assignment3.git
   cd DA6401_Assignment3
   ```

2. Install dependencies:
   ```bash
   pip install torch pandas numpy matplotlib tqdm
   ```

3. Update the file paths in both notebooks to point to your local dataset location.

4. Run the Jupyter notebooks:
   - For vanilla model: `Without_attention/vanilla_model.ipynb`
   - For attention model: `With_attention/attention_model.ipynb`

## Running the Models

To run the models:

1. Open the respective Jupyter notebook
2. Update the dataset path variables to point to your local dataset
3. Run each cell in sequence
4. The models will train and evaluate on the dataset
5. Results will be saved to the prediction CSV files

Both notebooks are self-contained with all necessary code for training and evaluation.

## Results

The attention-based model achieved approximately 60% accuracy on the test set, outperforming the vanilla Seq2Seq model which achieved approximately 55% accuracy. This demonstrates the benefit of the attention mechanism for the transliteration task, particularly for longer sequences.

## Visualizations

The repository includes visualization files that show:
- Character-level attention weights in the attention model
- Training and validation loss curves
- Sample predictions compared to ground truth
