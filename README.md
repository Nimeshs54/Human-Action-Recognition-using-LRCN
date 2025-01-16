# Human Action Recognition using LRCN

## 📂 Dataset

- **Dataset Link**: [UCF50 Dataset](https://www.crcv.ucf.edu/data/UCF50.php)
- **Paper Link**: [Long-term Recurrent Convolutional Networks for Visual Recognition and Description](https://arxiv.org/abs/1411.4389?source=post_page---------------------------)

### 📊 Dataset Summary

- **50** Action Categories (e.g., WalkingWithDog, HorseRace, Swing, PullUps, etc.)
- **25** Groups of Videos per Action Category
- **133** Average Videos per Action Category
- **199** Average Number of Frames per Video
- **320** Average Frame Width per Video
- **240** Average Frame Height per Video
- **26** Average Frames Per Second per Video

---

## 🚀 Project Overview

This project implements the **LRCN (Long-term Recurrent Convolutional Network)** approach by combining **Convolutional Neural Networks (CNNs)** and **Long Short-Term Memory (LSTM)** layers into a unified model:

1. **CNN Layers**: Extract spatial features from video frames.
2. **LSTM Layers**: Process spatial features at each time step to capture temporal dependencies.
3. **TimeDistributed Wrapper**: Allows the application of the same layer to every video frame independently, enabling the model to process video data in a single shot.

This end-to-end training approach enables the network to learn **spatiotemporal features**, resulting in a robust and efficient model for action recognition.

### Model Architecture

![LRCN](https://user-images.githubusercontent.com/37257980/148105499-88c3a6b4-f83c-4ff8-a1f1-dc77eb2093cc.png)

### Key Features of TimeDistributed

The [**`TimeDistributed`**](https://keras.io/api/layers/recurrent_layers/time_distributed/) layer ensures that each video frame is processed independently, transforming the input shape from:

`(no_of_frames, width, height, num_of_channels)`

to a format compatible with CNN layers. This makes it possible to feed an entire video into the model as a single batch.

---

## 📈 Model Performance

### Training and Validation Loss

![Train Loss vs Val Loss](https://user-images.githubusercontent.com/37257980/148108651-c68c6506-ece1-4a68-89a1-fbf4c4659d1f.png)

### Training and Validation Accuracy

![Train acc vs Val acc](https://user-images.githubusercontent.com/37257980/148108672-74730fba-dde2-4783-9687-79946aff2346.png)

---

## 🎥 Output

Here is an example of the model's action recognition output:

https://user-images.githubusercontent.com/37257980/148107701-a4587386-9347-4b9c-8d08-29ab7c40ef65.mp4

---

This project demonstrates the effectiveness of combining CNNs and LSTMs for robust human action recognition in video sequences.
