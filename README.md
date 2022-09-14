# Dynamic Multi-type Knowledge Tracing (DMKT) for Tuglet

This implementation of DMKT model for Tuglet datasets includes the following main classes:

1. **DMKT Transformer**: This class is used to process all data sequences of users into sequences of the same lengths. It inherits the `Dataset` class from Pytorch in order to return the data in the input format of Pytorch's `DataLoader`.
2. **DMKT Model**: contains the modified DMKT model and its associated operations.
2. **DMKT Agent**: This class initializes DMKT model and related features and functions such as optimizer, scheduler, etc. The `train` function in this class trains the model for `num_epochs` epochs and evaluates on the test set after each epoch.


## How to use the code?
1. Setup virtual environment and install all needed packages 
```
conda env create -f environment.yml
source init_env.sh
```
2. Put preprocessed datasets as .pkl files in `datasets` folder
3. Modify config file:
    - Train and evaluate on challenge questions: set `train_set` = 'questions' and `test_set` = 'questions`
    - Train on questions and evaluate on posttests: set `train_set` = 'questions' and `test_set` = 'posttests`
    - Train on questions and posttests, and evaluate on posttests: set `train_set` = 'questions_posttests' and `test_set` = 'posttests'

4. Run 

References:
[1] DMKT code: https://github.com/persai-lab/EDM2021-DMKT
[2] DMKT paper: Wang, Chunpai, Siqian Zhao, and Shaghayegh Sahebi. "Learning from Non-Assessed Resources: Deep Multi-Type Knowledge Tracing." International Educational Data Mining Society (2021).
[3] DKVMN paper: Zhang, Jiani, et al. "Dynamic key-value memory networks for knowledge tracing." Proceedings of the 26th international conference on World Wide Web. 2017.
