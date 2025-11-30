## Urban Sound Classification with Deep Learning

### 1. Introduction and Motivation
Urban sound classification has become a central research area for applications in urban informatics, acoustic surveillance, environmental recognition, and multimedia retrieval.

The fundamental objective is to enable automated systems to identify sounds such as horns, sirens, drilling, or street music—crucial elements in the sound perception of cities.

For many years, this field faced two main barriers:

1. **Absence of a common taxonomy**, which made comparison between studies difficult.

2. **Scarcity of large-scale annotated datasets**, with real and varied sounds from the urban environment.

These limitations were overcome starting in 2014, when Salamon, Jacoby, and Bello ([Salamon et al., 2014](salamon_urbansound_acmmm14.pdf)) created [UrbanSound8K](https://urbansounddataset.weebly.com/urbansound8k.html), a widely adopted dataset that has become the benchmark for evaluating deep learning models applied to urban sound.


### 2. Dataset and Urban Taxonomy
UrbanSound8K is an annotated subset of the UrbanSound Dataset, composed of approximately **8,732 samples** (**8.75 hours** of audio), grouped into **10 main classes** of urban sounds:

- air conditioner
- car horn
- children playing
- dog bark
- drilling
- engine idling
- gunshot
- jackhammer
- siren
- street music

Each recording is a maximum of **4 seconds** and has been carefully segmented and annotated for sound occurrence and acoustic salience (background sounds vs. foreground sounds).

The classes were selected based on the frequency of complaints recorded in the **NYC 311** system, making the dataset representative of the most common acoustic problems in modern cities.

Salamon's methodology also included a validation protocol in **10 folds**, ensuring the reproducibility of results and avoiding overlap between training and testing (slices of the same audio remain in the same fold).


### 3. Feature Extraction
#### Feature Selection - MFCCs
Much of the subsequent literature ([Piczak, 2015](Piczak2015-ESC-ConvNet.pdf); [Massoudi et al., 2021](Urban_Sound_Classification_using_CNN.pdf); [Tyagi et al., 2023](Urban+Sound+Classification+for+Audio+Analysis+Using+Long+Short-Term+Memory.pdf)) is based on Mel-scale cepstral coefficients (MFCCs), which represent the spectral content in a compact and perceptually meaningful way.

#### Extraction Process
- The signal is divided into **23.2 ms windows**, with **50% overlap**.

- For each window, **40 Mel filters** are calculated covering the range of 0–22,050 Hz.
- The **first 25 MFCC coefficients** are extracted per frame.

- Then, **aggregate statistics** (mean, variance, skewness, kurtosis, derivatives) are calculated to describe the complete sound.

This process results in vectors of approximately **225 attributes per sample**, allowing the sound to be represented as a time-frequency “image,” which serves as input for CNN networks.


### 4. CNN (Convolutional Neural Network) Based Models
#### 2D CNN - Spectrograms and MFCCs
The first deep learning models applied to urban sounds treated spectrograms as images.

[Piczak (2015)](Piczak2015-ESC-ConvNet.pdf) pioneered the use of **2D CNNs** on Mel spectrograms, demonstrating that this type of network outperforms classical methods such as SVM or Random Forest.

Later, [Massoudi, Verma and Jain (2021)](Urban_Sound_Classification_using_CNN.pdf) reinforced the effectiveness of this approach, using Mel-spectrograms derived from MFCCs as input to a CNN. The model achieved **91% accuracy**, standing out for its simplicity and efficiency.

[Barua et al. (2023)](A_Deep_Learning_Approach_for_Urban_Sound.pdf) compared several architectures (ANN, CNN, RNN, LSTM, and GRU) and **confirmed that CNNs offer the best balance between accuracy and computational cost**.

2D CNNs are effective because they extract local spatial patterns—such as textures and harmonics—from the time-frequency representations of audio, making them the dominant standard for acoustic classification.


### 5. Recurrent Neural Network (RNN) Based Models
#### Temporal Modeling — LSTM
Despite the success of CNNs, these networks treat sound as a static image, losing some information about temporal evolution.

To overcome this limitation, [Tyagi et al. (2023)](Urban+Sound+Classification+for+Audio+Analysis+Using+Long+Short-Term+Memory.pdf) proposed the use of **LSTM (Long Short-Term Memory) networks** applied to **temporal sequences of MFCCs**.

The model achieved **86% accuracy** and an **F1-score of 0.87** in UrbanSound8K, revealing that LSTMs are capable of capturing rhythmic patterns and long-term dependencies between frames, essential for distinguishing dynamic sounds such as sirens, footsteps, or engines.

The authors concluded that the combination of CNN (for spatial extraction) and LSTM (for temporal dependencies) — known as **CRNN (Convolutional Recurrent Neural Network)** — constitutes the most complete approach.


### 6. End-to-End Models — 1D CNNs and Direct Audio Learning

While previous approaches rely on MFCCs, Abdoli, Cardinal, and Koerich (2019) proposed an **end-to-end 1D-CNN** model that learns directly from the **raw audio signal (raw waveform)**.

This approach completely eliminates manual preprocessing, allowing the network to learn the relevant representations from the original sound.

The model achieved **89% accuracy** on UrbanSound8K and showed internal filters similar to human auditory patterns, confirming the ability of 1D CNNs to learn perceptually significant features.

In 2024, Zhao, Ye, Shen, and Liu ([Zhao et al., 2024](1D-CNN-based-audio-tampering.pdf)) applied a similar 1D-CNN architecture to audio tampering detection with ENF signals, reinforcing the potential of these networks in the direct analysis of acoustic signals.

1D CNNs offer advantages such as **simplicity, low number of parameters, and elimination of the feature engineering step**, although they may be more sensitive to noise and require careful normalization.


### 7. Discussion and Future Work
The literature reveals a clear methodological evolution:
- ``2014–2015``: Creation of the dataset and introduction of the first CNNs applied to spectrograms (Salamon, Piczak).

- ``2019–2021``: Consolidation of CNNs with MFCCs and emergence of end-to-end approaches (Abdoli, Massoudi).

- ``2023–2024``: Emphasis on temporal modeling (Tyagi) and direct audio processing (Zhao).

Current trends indicate that the **combination of CNNs and RNNs (CRNN)** represents the state of the art in urban sound classification, as it combines:

- **CNNs** → Capture of spatial and harmonic patterns.

- **RNNs/LSTMs** → Temporal and rhythmic modeling.

- **End-to-end approaches** → Elimination of dependence on manual features.

For future work, **hybrid architectures**, **data augmentation** techniques, and the use of **temporal-frequency attention** are suggested to improve the robustness and interpretability of the models.


### 8. Conclusion
Based on the analyzed works, it is observed that the greatest advances in urban sound classification derive from the transition between **traditional models based on fixed features and deep learning models** capable of extracting representations directly from the signal.

The adoption of **CNNs and LSTMs** has proven decisive, with the combined use of these architectures allowing the simultaneous exploration of the **frequency and temporal** dimensions of sound.

Thus, the choice to develop two models in this project—a **CNN** and an **RNN** (LSTM) applied to **UrbanSound8K**—is fully aligned with the current state and represents a solid, well-founded, and relevant approach in the context of artificial intelligence applied to sound.