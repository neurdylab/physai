# DeepPhysioRecon

Many studies of the human brain using functional magnetic resonance imaging (fMRI) lack concurrent physiological measures. Natural fluctuations in the body's physiology, such as breathing and heart rate, provide windows into one's health as well as critical functions such as cognition and emotion. In addition, physiological changes can heavily influence fMRI signals. As such, incorporating measurements of the body’s physiology into the analysis of fMRI data can substantially increase both the richness and interpretation of fMRI studies. To address this gap, we are developing frameworks for inferring continuous variations in respiration amplitude and heart rate directly from whole-brain fMRI dynamics. This project highlights the importance of studying brain-body interactions, proposes a tool that may enhance the efficacy of fMRI as a biomarker, and provides widely applicable open-source software.

---

### Young Adult Project

[REPO :simple-github:](https://github.com/neurdylab/deep-physio-recon){ .md-button }

In this project, we develop and rigorously evaluate a computational approach for inferring slow changes in respiratory volume (RV) and heart rate (HR) directly from the fMRI signal, without the need for fast multiband sampling or slice-based reconstructions. Leveraging a multi-task learning (MTL) framework, our approach simultaneously learns RV and HR, providing a robust method for enhancing fMRI data.

The model has undergone extensive validation through various experiments (e.g. downstream data analysis, examination of factors impacting model performance), a large subject pool that samples a range of fMRI paradigms (rest and multiple tasks), and model evaluation on an external (out-of-distribution) dataset with different fMRI acquisition parameters. Our main model was developed using resting-state fMRI data. However, we also developed a model that was trained on task data in order to assess brain-state dependency, ensuring that the inferred signals are contextually relevant. In addition to model development, this work carries out a meticulous assessment of the utility of the predicted signals, the performance under various conditions, and the interpretability of the model.

The resulting tool aims to enrich neuroimaging datasets by reconstructing missing or corrupted physiological data directly from fMRI data, and is specifically tailored for the young adult (~ 22-35 years old) population.


> <p align="center">
<img src="https://github.com/neurdylab/physai/blob/main/docs/assets/images/young.png?raw=true" width=800">
</p>

> The pipeline for estimating respiration volume (RV) and heart rate
(HR) signals from fMRI time-series dynamics is shown. Regions of interest are defined using 4 published
atlases that had been constructed from different imaging modalities, comprising areas in cerebral cortex,
white matter, subcortex, and the ascending arousal network. ROI time-series signals are extracted from
the fMRI volumes, detrended, bandpass filtered and downsampled. The preprocessed signals are provided
to a candidate network as input channels. A bidirectional LSTM network architecture is adapted for joint
estimation. The output of linear layers are RV and HR signals.

---

### Lifespan Project

[REPO :simple-github:](https://github.com/neurdylab/deep-physio-recon-lifespan){ .md-button }

In our lifespan project, we propose a novel framework that leverages Transformer-based architectures to reconstruct two key physiological signals—low-frequency respiratory volume (RV) and heart rate (HR) fluctuations—directly from fMRI data. This approach is specifically designed for and tested on a dataset of individuals aged 36-89 years old, encompassing a broad range of the adult lifespan.

We evaluate several model training and fine-tuning strategies, and find that incorporating young adult data during training improves model performance when predicting physiological signals in the aging cohort. This finding highlights the importance of cross-cohort learning and the adaptability of our models across different age ranges.

By inferring critical physiological variables directly from fMRI data, this work aims to broaden the study of brain-body interactions across a wide range of the adult lifespan, and to increase the efficacy of fMRI as a biomarker in aging research. 


> <p align="center">
<img src="https://github.com/neurdylab/physai/blob/main/docs/assets/images/lifespan.png?raw=true" height="500">
</p>

> Transformer seq2one (a) and Transformer seq2seq (b) model architectures. These models take fMRI time-series from specific brain regions of interest (ROIs) as input, and output the predicted physiological (RV and HR) time courses.