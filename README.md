# Imitation learning in sequential crowd counting

* This repository consist of implementation in "Imitation learning in sequential crowd counting using deep reinforcement learning"

## Abstract
Crowd counting in computer vision involves the utilization of advanced algorithms and image processing techniques to accurately estimate the number of individuals present in a given scene for applications such as surveillance and traffic control. The main approaches include detection-based methods and classification/regression-based methods. Another line of approach is to train an AI agent, like LibraNet, that can count the crowd in images sequentially through deep reinforcement learning (RL). However, the training of LibraNet that used Deep Q-learning is unstable and needs a long time for convergence. Therefore, this paper utilized imitation learning in Deep RL with a classification-based approach to speed up the convergence speed, combining the complementary strengths of the two approaches. The results show that training with the imitation learning loss and classification-based cross-entropy outperforms the original Q-learning loss in training the LibraNet.

## Instruction to run the code (Way1)
1. Download all the file and code from the [Onedrive](https://1drv.ms/f/s!Ahv-XQKk4-F9pGE97HwvACaHuXQR?e=oSU2Hz) (1.35GB), it contains all the models and results obtained.
2. Run the train.ipynb to train the model and evaluate.ipynb to evaluate the model


## Instruction to run the code (Way2)
1. Download the [ShangHaiTech](https://www.kaggle.com/datasets/tthien/shanghaitech) dataset (349MB)
2. Download the [VGG16 backbone pretrained](https://onedrive.live.com/?authkey=%21AM%5Fp2iKUk2B2viA&id=21A90DD283FC5F43%2114642&cid=21A90DD283FC5F43&parId=root&parQt=sharedby&parCid=7DE1E3A4025DFE1B&o=OneUp) on SHT Part_A, which is obtained from the author of [LibraNet](https://github.com/poppinace/libranet)
3. Follow the directory structure to place each of the files:
```
|-- evaluate.ipynb                 # After the Results folder is formed and training finish, can run this file for visualization 
|-- train.ipynb
|-- backbone.pth.tar               # VGG16 backbone pretrained on SHT Part_A
|-- ShanghaiTech
    |-- part_A
        |-- test_data 
            |-- images             # Contain the testing images
            |-- images-pt          # Contain the features of training images in .pt format (Auto generated)
            |-- ground-truth       # Contain the ground-truth of training images in .mat format
            |-- ground-truth-csv   # Contain the ground-truth of testing images in .csv format (Auto generated)
        |-- train_data    
            |-- images             # Contain the training images
            |-- images-pt          # Contain the features of training images in .pt format (Auto generated)
            |-- ground-truth       # Contain the ground-truth of training images in .mat format
            |-- ground-truth-csv   # Contain the ground-truth of training images in .csv format (Auto generated)
            
    |-- part_B
        |-- test_data
            |-- images
            |-- ground-truth
        |-- train_data
            |-- images
            |-- ground-truth
|-- Models                         # Contain the trained models
|-- Results                        # Contain the logs of the training

```
4. Download the required library to run the python code
5. Run the train.ipynb to obtain the result, 
* To use the VGG16 from pytorch, set USE_PYTORCH_VGG16 = True
* To use the VGG16 from 'backbone.pth.tar', set USE_PYTORCH_VGG16 = False
