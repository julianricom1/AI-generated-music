# AI Music Generation - Micro Project 1

This project is part of the coursework for Universidad de Los Andes (Colombia), developed for the first micro project of the course on neural networks and sequential data.

## 🎯 Project Objective

Train a neural network to generate music in the style of a single classical composer (e.g., Beethoven, Mozart) using symbolic musical data (MIDI). The model learns from real compositions and generates new sequences of notes that resemble the composer’s style.

## 🧠 Learning Goals

Through this project, you will:

- Structure sequential data for neural network training.
- Apply deep learning to musical time-series data.
- Build and train multi-output models with composite loss functions.
- Generate new musical sequences using the trained model.

## 🎼 Dataset

- 292 MIDI compositions by 19 classical composers (e.g., Beethoven, Chopin, Mozart).
- Only one composer and one instrument are used for each model.
- Features extracted from MIDI data:
  - `pitch` (categorical)
  - `step` (time since previous note)
  - `duration` (note length)
  - `velocity` (optional)

Feature extraction is done using the [`pretty_midi`](https://github.com/craffel/pretty-midi) library.

## 🧱 Model Design

The model is trained to predict the next note using a fixed-length context window of previous notes. It outputs multiple features for the predicted note:

- **pitch**: classification
- **step**, **duration**, **velocity**: regression

Implemented in **PyTorch**, using layers like `Embedding`, `LSTM`, `LayerNorm`, and `Linear`. The architecture and data pipeline are fully custom-built from scratch.

## 🛠️ Project Structure

- **Data preprocessing**: Extract note sequences and normalize continuous variables.
- **Custom PyTorch dataset**: Encodes sequences for training.
- **LSTM model**: Multi-headed architecture for classification and regression.
- **Loss function**: Composite loss combining `CrossEntropyLoss` and `L1Loss`.
- **Training loop**: Includes early stopping and performance tracking.
- **Generation**: Sample notes one at a time from the model and export results as MIDI and WAV.

## 🎧 Output

The model generates **3 audio files**, each with 200 AI-generated notes. MIDI outputs are converted to WAV for easier playback using online tools.

## 📎 Submission Contents

- Jupyter notebook with full implementation, training, and explanation (including the model architecture diagram).
- Diagram file (separately submitted).
- Three `.wav` files of generated music and three files with their respective seeds.

## 📌 Constraints

- Only the provided dataset was used.
- All code was implemented from scratch using PyTorch.
- No external data or pre-trained models.
- Code is original and executable by course evaluators.


