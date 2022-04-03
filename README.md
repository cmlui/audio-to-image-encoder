# audio-to-image-encoder 
This is the code for one of my thesis project models. The project is to experiement the feasibility of bi-directional cross-domain conversion with the use of machine learning techniques. This model consists of an autoencoder for audio conversion and GANs for image conversion. After the models were trained separately, they were used in combination to perform cross-domain conversion. To convert an audio clip to an image, the audio encoder first convert the audio(in form of spectrogram) to a latent vector. The latent vector is then processed by GANs to generate an image. To revert the image back into the audio clip, the generated image is projected into the GANs' latent space to get the latent vector back. The latent vector is then passed through the audio decoder to retrieve the spectrogram. The image below illustrates the mechanism. <br>

![model mechanism](https://github.com/cmlui/audio-to-image-encoder/blob/main/assets/mechanism.png?raw=true "model mechanism")

<hr>
The **audio_to_image.ipynb and image_to_audio.ipynb** call the trained model to perform the conversions. <br>
The trained models and the training notebooks are inside audio_model and image_model folders. <br>
random_audio stores an example audio for trial with the conversion<br>
audio_representations.npy and representation_from_image.npy are the intermediary latent representations<br>
generated_image.png is the image generated from GANs.<br>
requirement.txt listed the required packages<br><br>

---audio_model---<br>
audio_dataset is a placeholder. Please download data from http://www-mmsp.ece.mcgill.ca/Documents/Data/ (48k.zip) and place the unzipped contents into the folder. <br> 
Run preprocess and train to train the model. The model will be stored in the model folder<br>
autoencoder.ipynb contained the key functions of the model<br>
The other folders store the intermediary information.

---image_model---<br>
image_dataset is a placeholder. Please download data from https://www.kaggle.com/datasets/bryanb/abstract-art-gallery and place the images into the folder. <br>
gans_image.ipynb is the code for training the model. The trained model will be saved in gen_model.<br>
training_checkpoints will store the checkpoints during training for every 10 epochs.

<hr>
*The audio model is referenced from this project https://github.com/musikalkemist/generating-sound-with-neural-networks <br>