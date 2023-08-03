# Checking the suit and the number of any card.

Import any picture of a card and it will return the number and suit of the card. It displays the accuracy at the top.


## Training

I used the resnet model and retrained the data. I got a data set from Kaggle. The name of the kaggle dataset is Cards Image Dataset-Classification by Gerry. It contains a folder for every single card with at least 100 pictures per card. It seperates the data into train and test data. I imported this dataset into VScode. I then used the command line 

python3 train.py --model-dir=models/Card data/Card --epochs 150 -b 16

I used the resnet train.py. I directed the model to nthe models folder and set the dataset to the Card file. I ran it for 150 epochs and changed the batbch size to two times the default amount. 

## Test

To test the model I ran

/home/nvidia/jetson-inference/build/aarch64/bin/imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$NET/labels.txt $DATASET/test/'ace of spades'/1.jpg card.jpg 

I set the intial run to the imagnet file I modifed, set the test picture to the first ace of spades picture, and saved it to the card.jpg file. This specific test comes out with 63.95% ace of spades.

[Imgur](https://imgur.com/yBc9Apr)

## Running this project

1. In the jetson nano folder go to Jetson-Nano/python/training/classification
2. Replace the files in the folder with the files listed hear
4. Run this command
/home/nvidia/jetson-inference/build/aarch64/bin/imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$NET/labels.txt $DATASET/test/'ace of spades'/1.jpg card.jpg 
5. instead of /'ace of spades'/1.jpg choose any file that you want to test inside the test folder.
6. Run the code
7. Go to the card.jpg file to look at the image.

[View a video explanation here](video link)
