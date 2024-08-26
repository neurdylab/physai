## DeepPhysioRecon

Many studies of the human brain using functional magnetic resonance imaging (fMRI) lack physiological measurements, which substantially impacts theinterpretation and richness of fMRI studies. Natural fluctuations in autonomic physiology, such as breathing and heart rate, provide windows into critical functions including cognition, emotion, and health, and can heavily influence fMRI signals. We developed a framework tracing continuous variations in respiration amplitude and heart rate directly from whole-brain fMRI dynamics. This project highlights the importance of studying brain-body interactions, proposes a tool that may enhance the efficacy of fMRI as a biomarker, and provides widely applicable open-source software.

---

### Young Adult Project

[REPO :simple-github:](#){ .md-button }

In this project, we develop and rigorously evaluate a computational approach for inferring slow changes in respiratory volume (RV) and heart rate (HR) directly from the fMRI signal, without the need for fast multiband sampling or slice-based reconstructions. Leveraging a multi-task learning (MTL) framework, our approach simultaneously learns RV and HR, providing a robust method for enhancing fMRI data.

The model undergoes extensive validation through various experiments (e.g. downstream data analysis, factors impacting model performance), larger subject pools (e.g. various fMRI paradigms), and model evaluation on an external (out-of-distribution) dataset. We develop resting-state models as our main model. However, we also evaluated a task model to assess brain-state dependency, ensuring that the inferred signals are contextually relevant. This project goes beyond model development by thoroughly assessing the utility of the predicted signals, model performance, interpretability, and sensitivity.

The result is a meticulously validated tool that enriches neuroimaging datasets by reconstructing missing or corrupted physiological data, specifically tailored for the young adult population.