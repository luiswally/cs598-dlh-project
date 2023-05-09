# Project Final for CS598 DL4H in Spring 2023

This repository is the official implementation of [Project Final for CS598 DL4H in Spring 2023](https://www.gradescope.com/courses/519589).


## Requirements

To install requirements execute the following at the rooot directory of this repo:

```setup
conda env create --file ML39.txt
```
The environment above contains primarily:
- Python 3.9
- nltk
- gensim
- numpy
- sklearn
- keras

The above environment works on the following operating system and hardware: osx-arm64. Users may have to rectify operating system or software incompatabilities on their end.

Note, you will also need to download the ConceptNet term vectors (English-only, `numberbatch-en-19.08.txt.gz`) from [https://github.com/commonsense/conceptnet-numberbatch] and include in `\Data\english_conceptnet.txt` This is mentioned in the Jupyter Notebook, but included here as a reminder.

## Source Tree
    .
    ├── Data
    │   └── 500_Reddit_users_posts_labels.csv   : Anonymized annotated reddit dataset
    │
    ├── lexicon
    │   ├── suicidal_attempt.csv    : suicide severity lexicon, attempt
    │   ├── suicidal_behavior.csv   : suicide severity lexicon, behavior
    │   ├── suicidal_ideation.csv   : suicide severity lexicon, ideation
    │   └── suicidal_indicator.csv  : suicide severity lexicon, indicator
    │
    ├── results
    │   ├── cv          : cross-validation results for all 36 models
    │   └── images      : confusion matrix plots
    │
    └── notebooks
        └── confusion.ipynb         : Jupyter Notebook with 36 model experiments over the dataset


## Training/Evaluation

The training and evaluation of the CNN models and non-CNN models are performed in the Jupyter Notebook `confusion.ipynb`

## Results

Our model achieves performance on par with the original research! (see References)

![alt text](https://github.com/luiswally/cs598-dlh-project/blob/main/results/images/all-3plus1.png)

See below for comparison against original model best performance at Graded Precision for input I1.

| Model name         | This model GP   | Orig. model GP |
| ------------------ |---------------- | -------------- |
| CNN                |     82%         |      83%       |

![alt text](https://github.com/luiswally/cs598-dlh-project/blob/main/results/images/all-4.png)

![alt text](https://github.com/luiswally/cs598-dlh-project/blob/main/results/images/all-4.png)

## References

The replicated study is found here:

    Manas Gaur, Amanuel Alambo, Joy Prakash Sain, Ugur Kursuncu, Krishnaprasad Thirunarayan, Ramakanth Kavuluru, Amit Sheth, Randy Welton, and Jyotishman Pathak. Knowledge-aware assessment of severity of suicide risk for early intervention. In The World Wide Web Conference, pp. 514-525. ACM, 2019.

    @inproceedings{gaur2019knowledge,
       title={Knowledge-aware assessment of severity of suicide risk for early intervention},
       author={Gaur, Manas
                and Alambo, Amanuel
                and Sain, Joy Prakash
                and Kursuncu, Ugur
                and Thirunarayan, Krishnaprasad
                and Kavuluru, Ramakanth
                and Sheth, Amit
                and Welton, Randy
                and Pathak, Jyotishman},
       booktitle={The World Wide Web Conference},
       pages={514--525},
       year={2019},
       organization={ACM}
    }

The github repo can be found:

    ... Suicide Risk Severity Assessment tool\footnote{
        \url{https://github.com/jpsain/Suicide-Severity}
    }