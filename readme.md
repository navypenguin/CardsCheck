# Checking the suit and the number of any card.

Import any picture of a card and it will return the number and suit of the card. It displays the accuracy at the top.


## Training

I used the resnet model and retrained the data. I got a data set from Kaggle. The name of the kaggle dataset is Cards Image Dataset-Classification by Gerry. 
![Screenshot (6)](https://github.com/navypenguin/CardsCheck/assets/112725885/4f73e436-8e46-480a-ad11-190649b896b3)

It contains a folder for every single card with at least 100 pictures per card. It seperates the data into train and test data. I imported this dataset into VScode. I then used the command line 

python3 train.py --model-dir=models/Card data/Card --epochs 150 -b 16

I used the resnet train.py. I directed the model to nthe models folder and set the dataset to the Card file. I ran it for 150 epochs and changed the batbch size to two times the default amount. 

![Screenshot (5)](https://github.com/navypenguin/CardsCheck/assets/112725885/982aaf51-73ce-4d52-9e37-17af2460a085)

## Test

To test the model I ran

/home/nvidia/jetson-inference/build/aarch64/bin/imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$NET/labels.txt $DATASET/test/'ace of spades'/1.jpg card.jpg 

I set the intial run to the imagnet file I modifed, set the test picture to the first ace of spades picture, and saved it to the card.jpg file. This specific test comes out with 63.95% ace of spades.

![Screenshot (9)](https://github.com/navypenguin/CardsCheck/assets/112725885/fae57d05-3632-4194-bf86-519d56c2c601)

![Screenshot (7)](https://github.com/navypenguin/CardsCheck/assets/112725885/39a38610-58f0-4fd3-b95a-d10d11855db9)

## Running this project

1. In the jetson nano folder go to Jetson-Nano/python/training/classification
2. Replace the files in the folder with the files listed hear

 ![Screenshot (3)](https://github.com/navypenguin/CardsCheck/assets/112725885/0e4b6cd1-56fc-4e04-a7b4-660dec92b083)
 
4. Run this command
/home/nvidia/jetson-inference/build/aarch64/bin/imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$NET/labels.txt $DATASET/test/'ace of spades'/1.jpg card.jpg 
5. instead of /'ace of spades'/1.jpg choose any file that you want to test inside the test folder.
6. Run the code
7. Go to the card.jpg file to look at the image.

https://youtu.be/Gddk3Wu0rYk

