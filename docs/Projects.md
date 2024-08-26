## DeepPhysioRecon

Many studies of the human brain using functional magnetic resonance imaging (fMRI) lack physiological measurements, which substantially impacts theinterpretation and richness of fMRI studies. Natural fluctuations in autonomic physiology, such as breathing and heart rate, provide windows into critical functions including cognition, emotion, and health, and can heavily influence fMRI signals. We developed a framework tracing continuous variations in respiration amplitude and heart rate directly from whole-brain fMRI dynamics. This project highlights the importance of studying brain-body interactions, proposes a tool that may enhance the efficacy of fMRI as a biomarker, and provides widely applicable open-source software.

---

### Young Adult Project

[REPO :simple-github:](#){ .md-button }

In this project, we develop and rigorously evaluate a computational approach for inferring slow changes in respiratory volume (RV) and heart rate (HR) directly from the fMRI signal, without the need for fast multiband sampling or slice-based reconstructions. Leveraging a multi-task learning (MTL) framework, our approach simultaneously learns RV and HR, providing a robust method for enhancing fMRI data.

The model undergoes extensive validation through various experiments (e.g. downstream data analysis, factors impacting model performance), larger subject pools (e.g. various fMRI paradigms), and model evaluation on an external (out-of-distribution) dataset. We develop resting-state models as our main model. However, we also evaluated a task model to assess brain-state dependency, ensuring that the inferred signals are contextually relevant. This project goes beyond model development by thoroughly assessing the utility of the predicted signals, model performance, interpretability, and sensitivity.

The result is a meticulously validated tool that enriches neuroimaging datasets by reconstructing missing or corrupted physiological data, specifically tailored for the young adult population.

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

We evaluate several model training and fine-tuning strategies, with a significant finding that incorporating young adult data during training improves model performance when predicting physiological signals in the aging cohort. This highlights the importance of cross-cohort learning and the adaptability of our models across different age ranges.

Our framework successfully infers critical physiological variables directly from fMRI data, offering a powerful tool for studying brain-body interactions across a wide span of the adult lifespan. This work not only advances the field of neuroimaging but also enhances the efficacy of fMRI as a biomarker in aging research.

> <p align="center">
<img src="https://github.com/neurdylab/physai/blob/main/docs/assets/images/lifespan.png?raw=true" height="500">
</p>

> Transformer seq2one (a) and Transformer seq2seq (b) model architectures. These models take fMRI time-series from specific brain regions of interest (ROIs) as input, and output the predicted physiological (RV and HR) time courses.

---

### Other Research Inspired by DeepPhysioRecon Project
1. Addeh, A., Vega, F., Medi, P. R., Williams, R. J., Pike, G. B., & MacDonald, M. E. (2023). Direct machine learning reconstruction of respiratory variation waveforms from resting state fMRI data in a pediatric population. NeuroImage, 269, 119904. https://doi.org/10.1016/j.neuroimage.2023.119904


---
## Physiological Signal Patterns
<PLACE HOLDER>

### Heritability

### 

---
## Quality Assesment (QA)

While traditionally regarded as noise, systemic physiological processes are frequently shown to be linked with cognitive processes and may contribute valuable information to fMRI studies. Recognizing this, neuroimaging research increasingly draws upon concurrent recordings of peripheral physiology to enhance fMRI analysis. However, usefulness of physiological data is contingent upon the quality of the recordings as well as expertise in data handling. Quality assessment is not only a tedious process, but the assessments vary significantly between raters. While there are manual and template-based tools assessing peak detection quality (physiopy’s peakdet, PhysIO, etc.), and automated exclusion criteria based on statistical summary metrics, currently there are no automated approaches that can provide a quick quality check.

<p align="center">
<img src="https://github.com/neurdylab/physai/blob/main/docs/assets/images/qa.png?raw=true" width="500">
</p>

---

### Manual QA

We are working on designing a manual quality assessment tool for physiological data. This application will offers a streamlined interface for visualizing and evaluating data quality across various physiological signals, including but not limited to respiration and cardiac measures. 

With this app, users will efficiently navigate through individual subject waveforms, review timeseries data, and apply standardized quality labels. The tool will also enable textual annotations, providing context and insights into the quality of the waveforms.

[REPO :simple-github:](https://github.com/neurdylab/physio_QA_manual){ .md-button }

---

### Automated QA

As research practices generate increasingly large datasets, the need for efficient and scalable QA processes has become paramount. Manual QA, while thorough, is time-consuming and often subject to human error and variability. To address these challenges, we are motivated to develop automated QA solutions using deep learning (DL) techniques.

Automated QA systems, powered by DL, can rapidly and consistently assess the quality of physiological data across large datasets, identifying patterns and anomalies that might be overlooked in manual review. By leveraging the ability of DL models to learn from vast amounts of data, we can achieve more accurate and objective assessments, reduce the burden on researchers, and ensure that high-quality data is consistently used in analyses.

[REPO :simple-github:](https://github.com/neurdylab/physio_QA_dll){ .md-button }