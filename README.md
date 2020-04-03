# instrument classification
 Machine Learning Classification of Instruments

This is a project for ENSE 496AD Machine Learning. It classifies keyboard vs strings from the NSynth Dataset using various classifiers to compare different strengths of the classifiers. 
## Analysis:
Analysis of the process of the project and the results can be found in the [Project Proposal](https://github.com/AveryCameronUofR/instrument-classification/blob/master/ENSE%20496AD%20Project%20Proposal.pdf), the [Progress Report](https://github.com/AveryCameronUofR/instrument-classification/blob/master/ENSE%20496AD%20Progress%20Report.pdf), and the Final Report. Results and analysis of practices and rationale for feature extraction and classification used are included.

## How to use:
The Dataset folder contains the extracted features from the dataset for classification already. 

### Viewing features:
To view the extracted audio features graphically, [Feature Analysis](https://github.com/AveryCameronUofR/instrument-classification/blob/master/Feature%20Analysis.ipynb) and [SeeTwoFiles](https://github.com/AveryCameronUofR/instrument-classification/blob/master/SeeTwoFiles.ipynb) provide a view of the audio files of keyboard and piano with the various features that could be extracted.

Download the [NSynth Dataset](https://magenta.tensorflow.org/datasets/nsynth#files), the json/wav version. NSynth Train and Test sets are required for these files.

Launch jupyter notebooks, run the notebooks and view the different features.

Note: The folder structure should have the NSynth dataset(s) in the [/Dataset](https://github.com/AveryCameronUofR/instrument-classification/tree/master/Dataset/) folder with the RACK Dataset.

### Building the Dataset:
The dataset is already build and the results are found in the Extracted CSVs folder. 

To build the dataset yourself, You need the NSynth Dataset downloaded and in the dataset folder.
Run the [BuildDataset](https://github.com/AveryCameronUofR/instrument-classification/blob/master/BuildDataset.ipynb) file to extract the features to the CSVs. The feature_extract and build_dataset functions can be modifed to extract different features.

### Analyzing the features
The features extracted using Build Dataset can be analyzed using the XGBoost classifier in the [Feature Analysis](https://github.com/AveryCameronUofR/instrument-classification/blob/master/Feature%20Importance.ipynb) file. This provides insight into which features provide the most accurate prediction after extracting the dataset. 

### Running the Classifiers
The Classifier Prediction is in the [Prediction Models](https://github.com/AveryCameronUofR/instrument-classification/blob/master/Prediction%20Models.ipynb) file. This contains implementations of Scikit-learn's Binary Decision Trees, Random Forest, AdaBoost, KNN and SVM classifiers. Run the classifiers on the built dataset. 

### RACK Dataset:
The RACK Dataset is named from the initials of Avery Cameron and Raymond Knoor who recorded the sounds and annotated the dataset. This dataset is a way of analyzing the classifiers fit from the NSynth dataset on external audio files. The dataset contains piano notes and violin notes from C3 to A#3 to G5. The violin contains both bowed and short notes. The audio files are approximately four second WAV files with three seconds of a note playing and one second of die off with a sampling rate of 16KHz and mono audio output. The JSON file is annotated similar to the NSynth dataset to make extraction compatible. The exmple of prediction using the RACK dataset is found in [Rack Dataset](https://github.com/AveryCameronUofR/instrument-classification/blob/master/RACK%20Dataset%20Test.ipynb).

Note: The Violin Short audio files decrease accuracy, removing them from the CSV or the dataset and JSON file itself would increase accuracy. 
