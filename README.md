# Project_Latin
Using a custom VGG model to train on modified EMNIST in order to identify letters on Latin relics

It's sometimes difficult to identify a letter carved in historical relics like Roman tombstones, which was focused on in this project. With the help of image recognition, the project attempts to identify Latin letters on some of these artifacts.
Due of the lack of a befitting dataset for traditional Latin characters, the project instead uses EMNIST, a dataset available online consisting of handwritten letters and their classification. The dataset was trained on a custom VGG model, then a custom data file, which consists of a png of a character from a tombstone, is run through.
The main problem that was dealt with was the overfitting on the EMNIST model, since the diversity was not enough for the program to determine letters, and would rather be focused on the specific 28x28 image style used in the EMNIST dataset. To prevent this from happening, the project converts the EMNIST data into a binary file, consisted of either 1 or -1 depending on the brightness of the pixel. Each test file is also processed into a 28x28 picture, which is then also converted into a binary file so that it would most similarly match the modified EMNIST data.

Possible improvements: adjusting hyperparameters, implementing more models (ResNet), and of course finding a more reliable dataset.

Citations:
https://github.com/dipuk0506/SpinalNet/blob/master/MNIST_VGG/EMNIST_letters_VGG_and%20_SpinalVGG.py
https://github.com/ranihorev/Kuzushiji_MNIST/blob/master/KujuMNIST.ipynb  
