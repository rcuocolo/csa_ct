# Cartilaginous tumors study data

Model data developed in the Waikato Environment for Knowledge Analysis (WEKA) platform for the classification of cartilaginous tumors using radiomics from CT images
The "Files" folder contains the trained model (usable in weka with an appropriate dataset) and a text file with the training-testing run information. In this file, the weights used by the final model are available as well as all predictions and predicted probabilities for each case both in the training (through cross-validation) and test sets. Corresponding confusion matrices and accuracy metrics are also presented.

# Preparing the data

The model was trained on radiomic data extracted using [PyRadiomics](https://pyradiomics.readthedocs.io/en/latest/). Using bidimensional masks and the settings file included in the repository, an appropriate test set can be obtained from any CT exam of a cartilaginous tumor.
The extracted data should then be scaled by using the pickled Python objects also included in the repository. The pickled feature list contains the feature set on which to apply the scaler, while the scaler object contains the scikit-learn MinMaxScaler that can be loaded and fitted to the new data.
Finally, the resulting, scaled dataset should be saved either as a CSV or ARFF file to be read by WEKA. Please note WEKA expects the class to be present in the final column of the dataset, if present.

# How to load and use the model in WEKA

The WEKA workbench allows for a user-friendly implementation of machine learning algorithms. Its lower barrier to entry was partly behind its choice for the conduction of our analysis. The software is freely available online at this [link](https://www.cs.waikato.ac.nz/ml/weka/) together with detailed [documentation](https://waikato.github.io/weka-wiki/).
To load our model in WEKA, one can follow these steps:
- Open the Explorer module
- Load any dataset (not necessarily the one intended to apply the model to)
- Open the "Classify" tab of the Explorer module
- Right click in the "Result list" area (lower left) and "Load Model"
- Select the model file
- Select the "Supplied test set" option in the upper left
- Select the target dataset file
- Right click in the "Result list" area (lower left) on the loaded model
- Select the "Re-evaluate model on current test set" option

## Citation

- S. Gitto, R. Cuocolo, A. Annovazzi, V. Anelli, M. Acquasanta, A. Cincotta, D. Albano, V. Chianca, V. Ferraresi, C. Messina, C. Zoccali, E. Armiraglio, A. Parafioriti, R. Sciuto, A. Luzzati, R. Biagini, M. Imbriaco, L.M. Sconfienza, CT radiomics-based machine learning classification of atypical cartilaginous tumours and appendicular chondrosarcomas, EBioMedicine. 68 (2021) 103407. [https://doi.org/10.1016/j.ebiom.2021.103407](https://doi.org/10.1016/j.ebiom.2021.103407).

# License

Creative Commons Attribution 4.0 International (CC-BY-4.0). See "LICENSE" file for full details.
