# Rice Leaf Image Classification

This project uses a convolutional neural network (CNN) to classify rice leaf images into five categories: Normal Leaf, Blast, Narrow Brown Spot, Sheath Blight, and Tungro. It evaluates how well a basic image classifier performs on held-out images and examines which classes it most often confuses.

## Dataset and model

The notebook run used 3,150 labeled images, split into 2,205 training images, 472 validation images, and 473 test images. The split preserves the relative proportion of each class.

The PyTorch model takes 64 × 64 RGB images and uses three convolutional blocks, each with ReLU and max pooling. A fully connected classifier outputs one score per class. The model was trained from scratch for 12 epochs with Adam and a fixed learning rate of `0.001`. The weights from epoch 11 were selected because that epoch had the lowest validation loss.

## Results

| Metric | Value |
| --- | ---: |
| Held-out test accuracy | 84.36% |
| Test cross-entropy loss | 0.424 |
| Test macro F1-score | 0.843 |

The most frequent error was predicting **Normal Leaf** for **Narrow Brown Spot**, which happened on 18 test images. The notebook includes training and validation curves, a confusion matrix, a per-class report, and examples of misclassified images. These results describe performance on this test split.

## Run the notebook

1. Open the `.ipynb` file from this repository in Google Colab.
2. Run the first code cell and upload the dataset archive containing the five class folders.
3. Run the remaining cells in order to load the data, train the model, and evaluate it on the test set.

The notebook in this repository includes the saved outputs from the reported run.
