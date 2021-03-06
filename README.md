# ImageTextTranslation
![io1](https://user-images.githubusercontent.com/20552376/102013812-74360800-3d78-11eb-9b00-e0921528701f.jpg)<br>
![io2](https://user-images.githubusercontent.com/20552376/102013849-b19a9580-3d78-11eb-8d69-c3a7d1fd2002.jpg)

**Task here is to transliteration of english words present in images.**<br><br>
It consists of three sub-task:-<br><br>
1. Detection of english words in an image.<br>
2. Converting the detected word(crop images) in image to text.<br>
3. Transliteration of each text word from above step.

*Step 1*
# Detection of english words in image.<br>
The first step is to identify the location of English text in the image. Here I have used detectron for text detection. It should not recognize any other language text like Hindi etc. I have trained a model with a dataset of two languages (English and Hindi) with nearly 200 images. The model accurately identifies between English and Hindi. Model tries to put identified text into these classes if text in any other language is detected. <br>
The structure of the project is lil messed up, initially, I was training using my laptop, but for object detection, I had to move to collab, since detectron is not supported for windows. I didn't want to face any trouble later.:sweat_smile:

*Step 2*
# Converting the detected word(crop images) in image to text
This model's architecture is taken from https://arxiv.org/pdf/1507.05717.pdf. <br>
Once the english text is detected, the model will extract the features from the image, Either pretrained model or custom feature architecture can be used. Details are available in the paper.

*Step 3*
# Transliteration of each text word from above step.
Sequence-to-Sequence model with Attention Mechanism are used for Transliteration. Two layers of GRU are used in this model. Thanks to padhAI online course for providing the starter code.<br>

Once all the models have been trained, it can be used for Transliteration.

**Limitations**
* The input image should have either English or Hindi text, as the model is trained only on those images.
* Accuracy will improve by bringing in more data.
* The structure of this repo is little messed up, :sweat_smile: :sweat_smile:
* Converting curved text on images doesn't work that well, I have been working on straightening the text using OpenCV, Still in progress.  

Models - https://drive.google.com/drive/folders/19q-89TjeyaM2d8KbWdjWOjJV1Ow1ARi2?usp=sharing <br>
Datasets link - 
- https://github.com/GokulNC/NLP-Exercises/tree/master/Transliteration-Indian-Languages/Original-NEWS2012-data
- https://drive.google.com/file/d/1Z6Qxr-q-F54iYB2G1AyoDymBh64f5REZ/view

Credits.
* Transliteration started code for padhAI course.
* Seq2seq model's detail https://arxiv.org/pdf/1507.05717.pdf
* Test images downloaded from https://www.picxy.com/
