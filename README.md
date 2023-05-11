# PyTorch Implementation of Federated Learning Baselines

PyTorch-Federated-Learning provides various federated learning baselines implemented using the PyTorch framework. The codebase follows a client-server architecture and is highly intuitive and accessible.

If you find this repository useful, please let me know with your stars:star:. Thank you!

[English](README.md) | [简体中文](README.zh-CN.md)

* **Current Baseline implementations**: Pytorch implementations of the federated learning baselines. The currently supported baselines are FedAvg, FedNova, FedProx and SCAFFOLD:
  + [FedAvg](https://arxiv.org/abs/1602.05629) (Hugh Brendan McMahan et al., AISTATS 2017)
  + [FedNova](https://arxiv.org/abs/2007.07481) (Jianyu Wang et al., NeurIPS 2020) [:octocat:](https://github.com/JYWa/FedNova) 
  + [FedProx](https://arxiv.org/abs/1812.06127) (Tian Li et al., MLSys 2020) [:octocat:](https://github.com/litian96/FedProx) 
  + [SCAFFOLD](https://arxiv.org/abs/1910.06378) (Sai Praneeth Karimireddy et al.,ICML 2020) [:octocat:](https://github.com/ki-ljl/Scaffold-Federated-Learning) 

* **Dataset preprocessing**: Downloading the benchmark datasets automatically and dividing them into a number of clients w.r.t. federated settings. The currently supported datasets are MNIST, Fashion-MNIST, SVHN, CIFAR-10, CIFAR-100. Other datasets need to be downloaded manually.
* **Postprocessing**: Visualization of the training results for evaluation.


## Installation

### Dependencies

 - Python (3.8)
 - PyTorch (1.8.1)
 - OpenCV (4.5)
 - numpy (1.21.5)


### Install requirements

Run: `pip install -r requirements.txt` to install the required packages.

## Federated Dataset Preprocessing

This preprocessing aims to divide the entire datasets into a dedicated number of clients with respect to federated settings.
Depending on the the number of classes in each local dataset, the entire dataset are split into Non-IID datasets in terms of label distribution skew.


## Execute the Federated Learning Baselines

### Test Run
Hyperparameters are defined in a yaml file, e.g. "./config/test_config.yaml", and then just run with this configuration:

```
python fl_main.py --config "./config/test_config.yaml"
```


## Evaluation Procedures

Please run `python postprocessing/eval_main.py -rr 'results'` to plot the testing accuracy and training loss by the increasing number of epochs or communication rounds. 
Note that the labels in the figure is the name of result files

