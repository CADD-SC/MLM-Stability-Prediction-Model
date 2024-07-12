# MLM-Stability-Prediction-Model
Machine learning-based prediction model for Mouse Liver Microsomal (MLM) stability prediction

## Introduction ## 

Welcome to our repository, here we provide machine learning model to efficiently predict the Mouse Liver Microsomal (MLM) stability of target drug compounds in early stage of drug discovery process. Mouse liver microsomal stability testing is an important aspect of preclinical drug development. Understanding how long a compound remains stable in mouse liver microsomes helps in predicting the drug's metabolism and pharmacokinetics in vivo. This testing provides essential data for dose optimization and safety assessment in early drug discovery phases.

## Classification criteria ##

The model uses a half-life (t<sub>1/2</sub>) threshold:

</strong> If <em>t<sub>1/2</sub></em> > 30 min, the compound is <strong>Stable</strong> and belongs to class 1. If <em>t<sub>1/2</sub></em> ≤ 30 min, it is <strong>Not Stable</strong> and belongs to class 0.

## Dependencies ##

- Python ≥ 3.9
- scikit-learn ≥ 1.26.4
- numpy == 11.5.0
- hpsklearn == 1.0.3
- hyperopt == 0.2.7
- xgboost == 2.0.3
- rdkit
- pandas

## Execution ##
**To run the prediction:**

```
$ python model.py --prediction --file_name [filename] --model_path MCLint.pkl
```
<strong>Note:</strong> For the prediction step, prepare a .csv file containing SMILES without bioclass (e.g., test_set.csv)

**To run the validation:**

```
$ python model.py --validation --file_name [filename] --model_path MCLint.pkl
```
<strong>Note:</strong> For the validation step, prepare a .csv file containing SMILES with bioclass (0 or 1) (e.g., valid_set.csv)

**Output:**

Our model generates output in binary value (1 or 0), where 1 indicates compound to be stable, while 0 indicates unstable

 
**Please ensure that all the necessary files (MCLint.pkl, data_preprocessing.py, scaler, features.txt, input_file.csv, model.py) are kept in the working directory**
