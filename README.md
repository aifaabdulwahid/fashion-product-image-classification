# Fashion Product Image Classification

A TensorFlow/Keras convolutional neural network (CNN) that classifies fashion product images into four broad product categories using image data and labels from Kaggle.

## Dataset

- **Name:** [Fashion Product Images (Small)](https://www.kaggle.com/datasets/paramaggarwal/fashion-product-images-small)
- **Creator:** Param Aggarwal
- **Contents used:** Product images and `styles.csv`; the notebook uses each product's `masterCategory` label.
- **Classes:** Apparel, Accessories, Footwear, and Personal Care.

The notebook filters out the Home, Sporting Goods, and Free Items categories before training. The dataset is not included in this repository. Download it from Kaggle and follow its license and attribution requirements.

## Project Workflow

1. Load and inspect the product metadata and image files.
2. Keep the four selected product categories and split the data into stratified training, validation, and test sets (70% / 15% / 15%).
3. Resize images to 80 x 60 pixels, normalize pixel values, and augment training images with horizontal flips, zoom, and brightness variation.
4. Train a custom CNN with convolution, batch normalization, max pooling, dropout, and dense classification layers. Training uses class weights, early stopping, and learning-rate reduction on a plateau.
5. Evaluate the model with test accuracy, multiclass ROC AUC, a confusion matrix, and a classification report.

## Recorded Results

The notebook's saved run reports:

- **Test accuracy:** 97.46%
- **Test ROC AUC (one-vs-rest):** 0.9973

Results may vary if the dataset, environment, or training settings change.

## Run the Notebook

The notebook was written for Kaggle's notebook environment. To run it:

1. Download or open the notebook in Kaggle.
2. Add the [Fashion Product Images (Small) dataset](https://www.kaggle.com/datasets/paramaggarwal/fashion-product-images-small) as a notebook input.
3. Check `dataset_path` near the start of the notebook and update it to the location of the dataset's `myntradataset` directory if Kaggle mounts it at a different path.
4. Run the cells from top to bottom.

The notebook expects `styles.csv` and an `images/` folder containing product images named `<id>.jpg` inside `dataset_path`.

## Requirements

The notebook uses Python and the following packages:

- NumPy
- pandas
- Matplotlib
- TensorFlow / Keras
- scikit-learn
- Pillow
- seaborn

Kaggle notebooks provide a managed environment with many of these packages preinstalled. For a local setup, install the packages in your Python environment and update `dataset_path` to your local dataset directory.

## Repository Contents

- `custom_fashion_products_classificaion.ipynb` - data preparation, CNN training, and evaluation.
- `README.md` - project overview, dataset attribution, and run instructions.