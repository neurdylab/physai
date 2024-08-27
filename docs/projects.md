## DeepPhysioRecon

Many studies of the human brain using functional magnetic resonance imaging (fMRI) lack concurrent physiological measures. Natural fluctuations in the body's physiology, such as breathing and heart rate, provide windows into one's health as well as critical functions such as cognition and emotion. In addition, physiological changes can heavily influence fMRI signals. As such, incorporating measurements of the body’s physiology into the analysis of fMRI data can substantially increase both the richness and interpretation of fMRI studies. To address this gap, we are developing frameworks for inferring continuous variations in respiration amplitude and heart rate directly from whole-brain fMRI dynamics. This project highlights the importance of studying brain-body interactions, proposes a tool that may enhance the efficacy of fMRI as a biomarker, and provides widely applicable open-source software.

---

### Young Adult Project

[REPO :simple-github:](#){ .md-button }

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

[REPO :simple-github:](#){ .md-button }

In our lifespan project, we propose a novel framework that leverages Transformer-based architectures to reconstruct two key physiological signals—low-frequency respiratory volume (RV) and heart rate (HR) fluctuations—directly from fMRI data. This approach is specifically designed for and tested on a dataset of individuals aged 36-89 years old, encompassing a broad range of the adult lifespan.

We evaluate several model training and fine-tuning strategies, and find that incorporating young adult data during training improves model performance when predicting physiological signals in the aging cohort. This finding highlights the importance of cross-cohort learning and the adaptability of our models across different age ranges.

By inferring critical physiological variables directly from fMRI data, this work aims to broaden the study of brain-body interactions across a wide range of the adult lifespan, and to increase the efficacy of fMRI as a biomarker in aging research. 


> <p align="center">
<img src="https://github.com/neurdylab/physai/blob/main/docs/assets/images/lifespan.png?raw=true" height="500">
</p>

> Transformer seq2one (a) and Transformer seq2seq (b) model architectures. These models take fMRI time-series from specific brain regions of interest (ROIs) as input, and output the predicted physiological (RV and HR) time courses.


---
## Physiological Signal Patterns
A growing number of studies indicates that fMRI signals linked with breathing and cardiac activity may contain meaningful information about brain physiology and autonomic function. Yet, the behavioral relevance and heritability of low-frequency BOLD signals linked with physiology, and their large-scale patterns across the brain, are largely underexplored. In this work, we are investigating patterns of covariation between peripheral physiological signals and fMRI signals, and their association to individual differences and behavior.

---
## Physiological Variability Across Lifespan
The variability of the BOLD fMRI signal has been shown to be closely linked with aging. This work extends prior studies on BOLD variability and aging to investigate the subspace of low-frequency BOLD signal that is associated with physiological fluctuations measured from the body, focusing on natural changes in heart rate and respiration. Moreover, we are investigating whether the physiologically coupled signal changes may provide predictors of cognitive changes in the aging brain.
 
---
 
## State-Dependent Brain-Body Interactions
Levels of wakefulness are continually drifting, and come with marked changes in the characteristics of brain fMRI signals as well as changes in autonomic physiology. This work conducts a systematic examination of interactions between fMRI and several autonomic physiological measures (respiratory volume, heart rate, and pulse-wave amplitude) across vigilance states, where the latter is determined using EEG. One key finding is that the amount of covariation between fMRI and these physiological signals increases in states of lower vigilance (drowsiness and light sleep) compared to a state of higher alertness. These changes in fMRI-physiological covariance are also found to contribute, in part, to observed changes in fMRI functional connectivity across vigilance states. These findings contribute to our knowledge of human brain physiology and help to advance the interpretation of fMRI data. 

---
## Quality Assesment (QA)

While traditionally regarded as noise, systemic physiological processes are frequently shown to be linked with cognitive processes and may contribute valuable information to fMRI studies. Recognizing this, neuroimaging research increasingly draws upon concurrent recordings of peripheral physiology to enhance fMRI analysis. However, the usefulness of physiological data is contingent upon the quality of the recordings as well as expertise in data handling. Not only is quality assessment a tedious process, but the assessments can also vary significantly between raters. While there are manual and template-based tools for assessing peak detection quality (physiopy’s peakdet, PhysIO, etc.), and automated exclusion criteria based on statistical summary metrics, we are not aware of automated approaches that can provide a rapid, effective determination of quality on the whole-scan or windowed level.

<p align="center">
<img src="https://github.com/neurdylab/physai/blob/main/docs/assets/images/qa.png?raw=true" width="500">
</p>

---

### Manual QA

[REPO :simple-github:](https://github.com/neurdylab/physio_QA_manual){ .md-button }

We are working on designing a manual quality assessment tool for physiological data. This application will offer a streamlined interface for visualizing and evaluating data quality across various physiological signals, including but not limited to respiration and cardiac measures.

With this app, users will efficiently navigate through individual subject waveforms, review timeseries data, and apply standardized quality labels. The tool will also enable textual annotations, providing context and insights into the quality of the waveforms.

---

### Automated QA

[REPO :simple-github:](https://github.com/neurdylab/physio_QA_dl){ .md-button }

As research practices generate increasingly large datasets, the need for efficient and scalable QA processes has become paramount. Manual QA, despite being the current gold-standard, is time-consuming and often subject to human error and variability. To address these challenges, we are motivated to develop automated QA solutions using deep learning (DL) techniques.

Automated QA systems, powered by DL, can rapidly and consistently assess the quality of physiological data across large datasets, identifying patterns and anomalies that might be overlooked in manual review. By leveraging the ability of DL models to learn from vast amounts of data, we can achieve more accurate and objective assessments, reduce the burden on researchers, and ensure that high-quality data is consistently used in analyses.