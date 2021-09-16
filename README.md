# Deciphering Roman Tombstone Latin Characters with Image Recognition
Using a custom VGG model to train on modified EMNIST in order to identify letters on Latin relics

It's sometimes difficult to identify a letter carved in historical relics like Roman tombstones, which was focused on in this project. With the help of image recognition, the project attempts to identify Latin letters on some of these artifacts.
Due of the lack of a befitting dataset for traditional Latin characters, the project instead uses EMNIST, a dataset available online consisting of handwritten letters and their classification. The dataset was trained on a custom VGG model, then a custom data file, which consists of a png of a character from a tombstone, is run through.
The main problem that was dealt with was the overfitting on the EMNIST model, since the diversity was not enough for the program to determine letters, and would rather be focused on the specific 28x28 image style used in the EMNIST dataset. To prevent this from happening, the project converts the EMNIST data into a binary file, consisted of either 1 or -1 depending on the brightness of the pixel. Each test file is also processed into a 28x28 picture, which is then also converted into a binary file so that it would most similarly match the modified EMNIST data.

Possible improvements: adjusting hyperparameters, implementing more models (ResNet), and of course finding a more reliable dataset.

# Processing Input Data
Because the EMNIST dataset is configured in a specific way to recognize handwriting, the data had to modified in order to prevent overfitting. This included ridding the gradient of the character as well as thining it.
![Processed EMNIST](https://user-images.githubusercontent.com/32114848/133610137-f43613b4-37fc-4b2c-8f2e-176f18015abc.PNG)
# Training
![image](https://user-images.githubusercontent.com/32114848/133610243-d673f953-b2bf-431d-8bad-f4029f27751b.png)
# Testing
Each test data needed to be processed in different ways. First, it must be configured into a 28x28 black and white image, just like the training data provided by EMNIST.

![image](https://user-images.githubusercontent.com/32114848/133610366-ce993fbd-db5b-49f7-a66d-2cb476d51bb9.png)

Next, the image is turned into a binary image, built along with a 2-layer padding like the training data.
![image](https://user-images.githubusercontent.com/32114848/133610545-f3eadfc0-8f4d-4f7f-8c6d-ab326760d339.png)

Finally, we can run it through the model in order to obtain our result.
![image](https://user-images.githubusercontent.com/32114848/133610993-fc4cd7ce-6e20-4f62-903a-ec38664794ac.png)

Each letter is represented with a number on the alphabet from 1~26.
# Citations
https://github.com/dipuk0506/SpinalNet/blob/master/MNIST_VGG/EMNIST_letters_VGG_and%20_SpinalVGG.py
https://github.com/ranihorev/Kuzushiji_MNIST/blob/master/KujuMNIST.ipynb  
