# Digit-Recognition

Handwritten digit classification (0-9) using a Convolutional Neural Network (CNN) and the Kaggle Digit Recognizer dataset.

## Project structure

```text
Digit-Recognition/
├── data/
│   ├── train.csv
│   ├── test.csv
│   └── images.png
├── notebooks/
│   └── Digit-Recognition.ipynb
├── requirements.txt
├── .gitignore
└── README.md
```

## Requirements

- Windows 10/11
- Python 3.10 (recommended for TensorFlow 2.10 native Windows support)
- VS Code
- VS Code extensions: Python and Jupyter

## Run in VS Code

1. Extract the project ZIP.
2. Open VS Code.
3. Select **File > Open Folder** and choose the `Digit-Recognition` folder.
4. Open Terminal > New Terminal.
5. Create and activate a virtual environment:

   ```powershell
   py -3.10 -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```

   If PowerShell blocks activation, run this once in the current terminal:
   `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass`
   Then activate again.

6. Install dependencies:

   ```powershell
   python -m pip install --upgrade pip
   pip install -r requirements.txt
   ```

7. Open `notebooks/Digit-Recognition.ipynb`.
8. Click **Select Kernel** (top-right) and choose the Python interpreter inside `.venv`.
9. Run cells from top to bottom using **Run All**.

## What the project does

1. Loads training and test CSV files.
2. Separates digit labels from pixel values.
3. Normalizes pixels to the 0-1 range and reshapes images to 28×28×1.
4. Splits training data into training and validation sets.
5. Builds a CNN with convolution, max-pooling, dense, and dropout layers.
6. Compiles and trains the model using Adam and sparse categorical cross-entropy.
7. Plots accuracy and loss, evaluates the model, and displays a confusion matrix.
8. Predicts digits from the test dataset.
9. Saves the trained model and `submission.csv`.

## GitHub

The CSV files are included in this project. Each is below GitHub's 100 MB per-file limit, but the repository is large. To publish:

```bash
git init
git add .
git commit -m "Add Digit Recognition CNN project"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/Digit-Recognition.git
git push -u origin main
```

Replace `YOUR-USERNAME` with your GitHub username. Create an empty GitHub repository named `Digit-Recognition` first. Do not add a README/license/gitignore on GitHub when creating it, because this project already contains a README and .gitignore.

## Viva explanation

This project recognizes handwritten digits from 0 to 9. Each image contains 28×28 grayscale pixels. Pixel values are normalized to reduce their range. A CNN learns visual features through convolution and pooling layers. The dense output layer has 10 neurons, one for each digit, and softmax returns class probabilities. The model is trained with Adam and sparse categorical cross-entropy. Validation accuracy and a confusion matrix help evaluate its performance.
