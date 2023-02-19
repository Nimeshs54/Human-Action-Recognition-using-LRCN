# Human-Action-Recognition-using-LRCN

Dataset Link ----> https://www.crcv.ucf.edu/data/UCF50.php

The Paper link ----> https://arxiv.org/abs/1411.4389?source=post_page---------------------------

The Dataset Contains:

*   **`50`** Action Categories (WalkingWithDog, HorseRace, Swing, PullUps, etc...)

*   **`25`** Groups of Videos per Action Category

*   **`133`** Average Videos per Action Category

*   **`199`** Average Number of Frames per Video

*   **`320`** Average Frames Width per Video

*   **`240`** Average Frames Height per Video

*   **`26`** Average Frames Per Seconds per Video


## Project overview:
I implemented the LRCN approach by combining CNN and LSTM layers in a single model. The Convolutional layers are used for spatial feature extraction from the frames, and the extracted spatial features are fed to LSTM layer(s) at each time-steps for temporal sequence modeling. This way the network learns spatiotemporal features directly in an end-to-end training, resulting in a robust model. 

![LRCN](https://user-images.githubusercontent.com/37257980/148105499-88c3a6b4-f83c-4ff8-a1f1-dc77eb2093cc.png)

We will also use [**`TimeDistributed`**](https://keras.io/api/layers/recurrent_layers/time_distributed/) wrapper layer, which allows applying the same layer to every frame of the video independently. So it makes a layer (around which it is wrapped) capable of taking input of shape `(no_of_frames, width, height, num_of_channels)` if originally the layer's input shape was `(width, height, num_of_channels)` which is very beneficial as it allows to input the whole video into the model in a single shot. 


## Model's Loss & Accuracy Curves

![Train Loss vs Val Loss](https://user-images.githubusercontent.com/37257980/148108651-c68c6506-ece1-4a68-89a1-fbf4c4659d1f.png)

![Train acc vs Val acc](https://user-images.githubusercontent.com/37257980/148108672-74730fba-dde2-4783-9687-79946aff2346.png)



## Output:

https://user-images.githubusercontent.com/37257980/148107701-a4587386-9347-4b9c-8d08-29ab7c40ef65.mp4


