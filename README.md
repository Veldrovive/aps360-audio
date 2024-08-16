# Contrastive Audio Genre Prediction

This repository contains code necessary to train a contrastive embedding model on the MTG dataset which can then be used in genre prediction (e.g. on the GTZAN dataset).

All code an documentation can be found in [/project.ipynb](/project.ipynb).

Up to the section titled "High Level Classifier Training Loop", you should run every cell. This is all setup and loading the data. Each section after that can be run individually to produce results for a specific type of model.


This project provides scripts to train a contrastive model on the MTG dataset. The contrastive model is used to learn representations of music tracks that can be used for tasks like music genre classification, music recommendation, and other audio-related tasks.

Pretrained Models can be found [https://drive.google.com/drive/folders/1gqYGBAECBNKzyEfkcmb7Uh9Otz_X82I1?usp=sharing](here.)

## Training the Contrastive Model

To train the contrastive model on the MTG dataset, use the provided scripts. The scripts offer several customizable options, which are detailed below.

### Usage

Run the training script with the following options:

```bash
python training.py [options]
```

### Options

- `-h`, `--help`:  
  Show the help message and exit.

- `-b BATCH_SIZE`, `--batch_size BATCH_SIZE`:  
  Set the batch size for training.  
  **Default:** `256`

- `-l LEARNING_RATE`, `--learning_rate LEARNING_RATE`:  
  Set the learning rate for training.  
  **Default:** `0.001`

- `-e EPOCHS`, `--epochs EPOCHS`:  
  Set the number of epochs for training.  
  **Default:** `25`

- `-mo MODEL`, `--model MODEL`:  
  Specify the model to use for training the contrastive model.  
  Options: `GTZANContrastiveModelXLarge`, `GTZANContrastiveModelLarge`, `GTZANContrastiveModel`  
  **Default:** `GTZANContrastiveModelLarge`

- `-me MEL_AUGMENT_TYPE`, `--mel_augment_type MEL_AUGMENT_TYPE`:  
  Choose the type of mel spectrogram augmentation to use. Choose 1 for no overlap, 2 for complete overlap and 3 for partial overlap of upto 50% in the positive examples.  
  Options: `1`, `2`, `3`  
  **Default:** `1`

- `-f RECOVERY_FOLDER_NAME`, `--recovery_folder_name RECOVERY_FOLDER_NAME`:  
  Specify the name of the folder to recover the model from. If set to `None`, a new folder will be created.  
  **Default:** `None`

### Example Command

To train the model using default parameters:

```bash
python training.py
```

To train the model with a different batch size and learning rate:

```bash
python training.py --batch_size 128 --learning_rate 0.0005
```

## Notes

- Make sure the MTG dataset is properly prepared and available before running the training script.
- The default model is `GTZANContrastiveModelLarge`. If you wish to experiment with other models, specify the `--model` option accordingly.
- For better results, try experimenting with different mel spectrogram augmentation types.
Here's a Markdown draft for the README file, including the new script `train_classification_model_n_plots.py`:



## Training the Contrastive Model on the MTG Dataset

To train the contrastive model on the MTG dataset, use the provided `train_contrastive_model.py` script. The script offers several customizable options.

### Usage

Run the training script with the following options:

```bash
python train_contrastive_model.py [options]
```

### Options

- `-h`, `--help`:  
  Show the help message and exit.

- `-b BATCH_SIZE`, `--batch_size BATCH_SIZE`:  
  Set the batch size for training.  
  **Default:** `256`

- `-l LEARNING_RATE`, `--learning_rate LEARNING_RATE`:  
  Set the learning rate for training.  
  **Default:** `0.001`

- `-e EPOCHS`, `--epochs EPOCHS`:  
  Set the number of epochs for training.  
  **Default:** `25`

- `-mo MODEL`, `--model MODEL`:  
  Specify the model to use for training the contrastive model.  
  Options: `GTZANContrastiveModelXLarge`, `GTZANContrastiveModelLarge`, `GTZANContrastiveModelMedium`, `GTZANContrastiveModelSmall`  
  **Default:** `GTZANContrastiveModelLarge`

- `-me MEL_AUGMENT_TYPE`, `--mel_augment_type MEL_AUGMENT_TYPE`:  
  Choose the type of mel spectrogram augmentation to use.  
  Options: `1`, `2`, `3`  
  **Default:** `1`

- `-f RECOVERY_FOLDER_NAME`, `--recovery_folder_name RECOVERY_FOLDER_NAME`:  
  Specify the name of the folder to recover the model from. If set to `None`, a new folder will be created.  
  **Default:** `None`

### Example Command

To train the model using default parameters:

```bash
python train_contrastive_model.py
```

To train the model with a different batch size and learning rate:

```bash
python train_contrastive_model.py --batch_size 128 --learning_rate 0.0005
```

## Training the Classification Model on the GTZAN Dataset

To train a classification model on the GTZAN dataset, use the `train_classification_model_n_plots.py` script.

### Usage

Run the training script with the following options:

```bash
python train_classification_model_n_plots.py [options]
```

### Options

- `-h`, `--help`:  
  Show the help message and exit.

- `-b BATCH_SIZE`, `--batch_size BATCH_SIZE`:  
  Set the batch size for training.

- `-l LEARNING_RATE`, `--learning_rate LEARNING_RATE`:  
  Set the learning rate for training.

- `-e EPOCHS`, `--epochs EPOCHS`:  
  Set the number of epochs for training.

- `-f MODEL_FOLDERS`, `--model_folders MODEL_FOLDERS`:  
  Specify the folders to load the contrastive model trained on MTG dataset. 

### Example Command

To train the classification model using default parameters:

```bash
python train_classification_model_n_plots.py
```

To train the model with a different batch size and learning rate:

```bash
python train_classification_model_n_plots.py --batch_size 128 --learning_rate 0.0005
```

## Notes

- Make sure the datasets (MTG and GTZAN) are properly prepared and available before running the training scripts.
- Experiment with different parameters to optimize the model performance.