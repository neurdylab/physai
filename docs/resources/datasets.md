We are committed to sharing all data related to our project. This will include list of subjects that passed quality assurance and were used in our projects, along with the associated quality assurance code. The data encompass several significant cohorts, such as HCP-YA (yound adult), HCP-A (aging), and NKI-RS (Rockland Sample) datasets, as well as Vanderbilt's internal collections.

Currently, we are in the process of preparing these resources for public release. Please stay tuned for updates as we finalize the preparation and obtain the necessary permissions.


## Human Connectome Project

### Young Adult (HCP-YA)

| Info                   | Details                                                |
| ---------------------- | ------------------------------------------------------ |
| Paradigm               | Resting-state                                          |
| Physiological Measures | Respiration (belt), Cardiac (PPG)                      |
| Quality Control        | Passed in both Power et al. (2020)^1^ and Xifra-Porxas et al. (2021)^2^. |
| Subjects Passed QA | [HCP-YA_REST_clean_physio_subset](https://github.com/neurdylab/deep-physio-recon/blob/main/IMAGINGNEURO2025/meta/HCP1200_REST_clean_physio_subset.txt) |
| Link to Public Dataset | [Young Adult Cohort](https://www.humanconnectome.org/study/hcp-young-adult) |

| Info                   | Details                                                |
| ---------------------- | ------------------------------------------------------ |
| Paradigm               | Task                                                   |
| Tasks  | EMOTION, GAMBLING, LANGUAGE, MOTOR, RELATIONAL, SOCIAL, WORKING MEMORY |
| Physiological Measures | Respiration (belt), Cardiac (PPG)                      |
| Quality Control | Met automated quality-control criteria as defined in this [QA script](https://github.com/neurdylab/deep-physio-recon/blob/main/IMAGINGNEURO2025/preprocessing/automated_qa_hcp.m) |
| Subjects Passed QA| [HCP-YA_TASKX_clean_physio_subset](https://github.com/neurdylab/deep-physio-recon/blob/main/IMAGINGNEURO2025/meta/)   
| Link to Public Dataset | [Young Adult Cohort](https://www.humanconnectome.org/study/hcp-young-adult) |


### Aging (HCP-A)

 | Info      | Details                        |
| ----------- | ------------------------------------ |
| Paradigm | resting-state |
| Physiological Measures | Respiration (belt) and Cardiac (ppg) |
| Criteria | Signal quality was manually assessed by verifying reliable heartbeat detection in the PPG signal and the presence of interpretable low-frequency respiratory dynamics (e.g., variations in breathing depth and rhythm) in the respiratory belt signal. The subset was identified as high quality by Shiyu Wang and Catie Chang, using the subject list from Fan et al. (2025) as a reference.^3^ |
| Subjects Passed QA | [HCP-A_REST_clean_physio_subset](https://github.com/neurdylab/deep-physio-recon-lifespan/blob/main/dataset/hcpa_qa_sub_sess_list.txt) |
| Link to Public Dataset | [HCP Aging Cohort](https://www.humanconnectome.org/study/hcp-lifespan-aging) |


## NKI-Rockland Sample
!!! note 
    In prep.

---

<h3> References </h3>

1.  Power JD, Lynch CJ, Dubin MJ, et al (2020). Characteristics of respiratory measures
in young adults scanned at rest, including systematic changes and “missed” deep
breaths. Neuroimage 204:116,234

2.  Xifra-Porxas A, Kassinopoulos M, Mitsis GD (2021). Physiological and motion
signatures in static and time-varying functional connectivity and their subject
identifiability. Elife 10:e62,324

3.  Fan J, Juttukonda MR, Goodale SE, Wang S, Orbán C, Varadarajan D, Polimeni JR, Chang C, Salat DH, Chen JE (2025). Functional MRI signatures of autonomic physiology in aging. Communications Biology, 8(1), 1287.