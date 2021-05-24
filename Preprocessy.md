# Preprocessy

## Team members
* Bhumika Kothwal
* Devayani Shivankar
* Jhagrut Lalwani
* Samina Attari 

## Mentors
* Palak Mantry
* Parth Shah
* Priyesh Vakharia
* Riya Gupta
* Yash Tailor
* Mohammed Mehdi Patel
* Saif Kazi

## Description

`Preprocessy` is a library that provides data preprocessing pipelines for machine learning. It bundles all the common preprocessing steps that are performed on the data to prepare it for machine learning models. It aims to do so in a manner that is independent of the source and type of dataset. Hence, it provides a set of functions that have been generalised to different types of data.

The pipelines themselves are composed of these functions and flexible so that the users can customise them by adding their processing functions or removing pipeline functions according to their needs. The pipelines thus provide an abstract and high-level interface to the users.

> GitHub repo link: [Link to repository](https://github.com/preprocessy/preprocessy.git)

## Features

The goal of this project is to simplify the data preprocessing and make the process dataset agnostic. The library contains several functions that can be used independantly or as a part of a pipeline. A pipeline basically a sequence of operations made on the dataset. The pipelines are configured with good defaults out-of-the-box but are flexible as well so  you can add new custom functions and tweak the pipeline. `Preprocessy` also has a small dependency tree consisting of `pandas` and `scikit-learn` which we are planning to further reduce.

List of Functions includes - 

- Reading data from different types of files - `.csv, .tsv, .xls, .xlsx, .xlsm, .xlsb, .odf, .ods, .odt`
- Functions for Handling Null values
- Outlier detection and removal
- Normalization and Scaling
- Ordinal and Categorical Data Encoding
- Feature Selection Algorithms
- Data splitting functions
- Serializing and Deserializing Pipeline configurations

These functions can be used independantly or you can use them to build your own pipeline by inheriting for the [Base Pipeline Class](https://github.com/preprocessy/preprocessy/blob/master/preprocessy/pipelines/_base.py).

Other features include -

- Customizable pipelines
- Easy-to-use API
- Thoroughly tested (Refer [Coverage](https://github.com/preprocessy/preprocessy/blob/master/CONTRIBUTING.md#running-test-coverage))
- Actively maintained

## Tech stack

For Production
- Pandas
- Scikit-learn

For Development
- Black (Code Formatting)
- Flake8 (Linting)
- Pre-commit (Pre-commit hooks)
- Pytest (Testing)
- Coverage (Test coverage)
- Sphinx (Documentation)

## Applications and Use Cases

`Preprocessy` has a simple, pythonic, high-level API that makes it easy to use for new-commers to the field of data science yet flexible enough for experts to customize and suit their needs. 

Typical Use Cases include -

- `Preprocessy` can be used for quick and rough data preprocessing and model training to get a baseline model. This makes it easier to get a lower bound for accuracy and speeds up the iterative ML process.

- Often in machine learning the sources of data for training and testing differ from each other. Therefore, it becomes important to apply transformations to the test data as well. You can build and save pipelines using `Preprocessy` and use them for training and for production

- If your data requires more customization, you can build your custom functions that follow the same `params` style function signature of the built-in functions and use them in your pipelines.

## What did you learn from this project

1. Bhumika Kothwal
   
    Learned about different processing techniques and when to apply which method, about Unittests in python. Learned about working on project with submitting PRs, understanding others' code, resolving conflicts, reviewing PRs. 

2. Devayani Shivankar

    This was my first time contributing to an open source project. It was such a great opportunity to explore what all git command line  has in store. Coming to the actual project, I learnt how pipelines can be used to train datasets.

3. Jhagrut Lalwani
       
    Learned about Git version control, understood more about working of pipelines and how to improve processing of data thereby improving the model. Worked on feature selection using SelectKBest.  

4. Samina Attari

    It was a great experience for me to work on `Preprocessy`. I got an opportunity to learn Git, a version control system, and understand the structure of pipelines and work with it and also data cleaning and data preprocessing which forms the basis of the project.


## Future scope

- Currently, the functions only support pandas dataframes. We plan to expand this to other datatypes such as images, audio and text

- Focus on optimizing the existing pipelines and functions

- Provide a set of pre-configured pipelines

- Build concrete documentation and community for the project

## Contributing

`Preprocessy` is an open-source project looking for contributors. Refer [CONTRIBUTING.md](https://github.com/preprocessy/preprocessy/blob/master/CONTRIBUTING.md) for more details.


## Screenshots

The project board shows the current status of the project. We use it to keep track of open issues and PRs

![Project-Board](https://drive.google.com/uc?export=view&id=1I0lbdyQxCv8HKwHg6PBRYN0x31_H32Kb) 

### Performance

- Feature Selection - We trained a synthetic dataset consisting of random number of features ranging from 50-100, without preprocessing and with `preprocessy.feature_selection.SelectKBest` which selects the top K features.

![Performance](https://drive.google.com/uc?export=view&id=1NyO_fHyZ3JJGdRdVg9sb2Qr9Qd_5ygfH)

See [evaluations](https://github.com/preprocessy/preprocessy/tree/master/evaluations) for more details.

### Documentation

We are currently working on documentation for the project. The documentation can be found at [preprocessy.readthedocs.io](https://preprocessy.readthedocs.io/en/latest/)

Refer [CONTRIBUTING.md](https://github.com/preprocessy/preprocessy/blob/master/CONTRIBUTING.md) for more details.

![Documentation](https://drive.google.com/uc?export=view&id=1q33T_JfNmFNjNEyxjKsvVgDLtEUuq7o1)