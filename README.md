# UrbanSound8K Classification - Deep Learning Approaches for Audio Recognition

This project was developed for the "Machine Learning II" course and ains to developed deep learning classifiers for urban sund data, using the UrbanSound8K dataset. Classifiers must be able to identify which of 10 classses of urban sounds (sirens, dog barking, drills, etc.) a previously unseen audio clip belongs to.

For this we implemented: **Convolutional Neural Network (CNN)** and **Recurrent Neural Network (RNN)**.

## Requirements:

    - librosa 
    - matplotlib 
    - ipython 
    - scipy 
    - pandas 
    - numpy 
    - seaborn 
    - soundfile 
    - scikit-learn 
    - tensorflow


<br>

## The Project
The goal of this project is to develop two types of neural networks capable of correctly classifying portions of audio correctly.


### The Dataset
In this project, we use the **"UrbanSound8K** dataset, which can be obtained through the following link: https://urbansounddataset.weebly.com/urbansound8k.html.

This dataset contains 8732 labeled audio clips lasting approximately 4 seconds. The audio clips are labeled according to the following 10 classes:
- air conditioner
- car horn
- children playing
- dog bark
- drilling
- enginge idling
- gun shot
- jackhammer
- siren
- street music


### Models
- CNN
- RNN

<br>

## About the repository:
- ``Exploratory_Data_Analysis.ipynb`` -> initial notebook for data exploration and processing
- ``CNN.ipynb`` -> notebook with CNN model implementation
- ``RNN.ipynb`` -> notebook with RNN model implementation
  
<br>

- **images** -> directory with images used in this project
- **results_images** -> directory with images of the model results
- **results_analysis** -> directory with graphs analyzing the results
- **UrbanSound8K** -> directory with audio and metadata

<br>

## References

- A Review of DeepFool: a simple and accurate method to fool deep neural networks | by Adrian Morgan | Machine Intelligence and Deep Learning | Medium. (n.d.). Retrieved November 30, 2025, from https://medium.com/machine-intelligence-and-deep-learning-lab/a-review-of-deepfool-a-simple-and-accurate-method-to-fool-deep-neural-networks-b016fba9e48e
- Abdoli, S., Cardinal, P., & Lameiras Koerich, A. (2019). End-to-end environmental sound classification using a 1D convolutional neural network. Expert Systems with Applications, 136, 252–263. https://doi.org/10.1016/J.ESWA.2019.06.040
- Barua, S., Akter, T., Musa, M. A. S., & Azim, M. A. (2023). A Deep Learning Approach for Urban Sound Classification. International Journal of Computer Applications, 185(24), 8–14. https://doi.org/10.5120/ijca2023922991
- Massoudi, M., Verma, S., & Jain, R. (2021). Urban Sound Classification using CNN. Proceedings of the 6th International Conference on Inventive Computation Technologies, ICICT 2021, 583–589. https://doi.org/10.1109/ICICT50816.2021.9358621
- Mienye, I. D., Swart, T. G., Obaido, G., Mienye, I. D., Swart, T. G., & Obaido, G. (2024). Recurrent Neural Networks: A Comprehensive Review of Architectures, Variants, and Applications. Information 2024, Vol. 15, 15(9). https://doi.org/10.3390/INFO15090517
- Phan, H., Koch, P., Katzberg, F., Maass, M., Mazur, R., & Mertins, A. (n.d.). Audio Scene Classification with Deep Recurrent Neural Networks.
- Piczak, K. J. (2015). ENVIRONMENTAL SOUND CLASSIFICATION WITH CONVOLUTIONAL NEURAL NETWORKS. https://doi.org/10.5281/zenodo.12714
- Salamon, J., Jacoby, C., & Bello, J. P. (2014). A dataset and taxonomy for urban sound research. MM 2014 - Proceedings of the 2014 ACM Conference on Multimedia, 1041–1044. https://doi.org/10.1145/2647868.2655045
- Tyagi, S., Aggarwal, K., Kumar, D., & Garg, S. (n.d.). Urban Sound Classification for Audio Analysis Using Long Short-Term Memory.
- Zhao, H., Ye, Y., Shen, X., & Liu, L. (2024). 1D-CNN-based audio tampering detection using ENF signals. Scientific Reports, 14(1). https://doi.org/10.1038/s41598-024-60813-0


<br>

## Authors

* **Beatriz Pereira** - *Bioinformatics - FCUP* - [Beapereirax](https://github.com/Beapereirax) 
* **Carolina Leite** - *Bioinformatics - FCUP* - [caroleite05](https://github.com/caroleite05)
* **Lara Gonçalves** - *Bioinformatics - FCUP* - [laragoncalves1375](https://github.com/laragoncalves1375)

<br>

## Link to the course:
This course is part of the **first semester** of the **third year** of the **Bachelor's Degree in Bioinformatics** at **FCUP, ICBAS and FFUP** in the academic year 2025/2026. You can find more information about this course at the following link:

###

[![Link to Course](https://img.shields.io/badge/Link%20to%20Course-blue?style=for-the-badge)](https://sigarra.up.pt/fcup/pt/ucurr_geral.ficha_uc_view?pv_ocorrencia_id=570360) <br>
[![FCUP](https://img.shields.io/badge/FCUP-lightgrey?style=for-the-badge)](https://www.up.pt/fcup/pt/)
[![ICBAS](https://img.shields.io/badge/ICBAS-lightgrey?style=for-the-badge)](https://www.up.pt/icbas/pt/)
[![FFUP](https://img.shields.io/badge/FFUP-lightgrey?style=for-the-badge)](https://sigarra.up.pt/ffup/pt/web_page.Inicial)

###


*Aprendizagem Computacional II - FCUP - 2025/2026*