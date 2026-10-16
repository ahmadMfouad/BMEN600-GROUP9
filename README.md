# BMEN 600 Project
## Group 9
## Ahmed Osman, Hanna Musnicka, Sheikh Falah Sheikh Hasan, Rubbina Bhatti

## Older Population Fall Risk
### Falls are the leading cause of injury death among adults over 65. Men and women fall at similar rates, but women report substantially more fall-related injuries, so the disparity lies in outcome rather than frequency.

### Falls are self-reported by telephone, so recall bias is likely, and the survey excludes adults in nursing homes.
## Dataset

**GSTRIDE** v1.0 (García-Villamil Neira et al.), Zenodo: [10.5281/zenodo.8003441](https://doi.org/10.5281/zenodo.8003441), licensed CC BY 4.0.

163 older adults (45 men, 118 women, aged 70–98). Each participant has one walking test recorded with a foot-mounted IMU (mean duration 21.4 ± 7.1 min) plus a clinical battery: 4-m gait speed, hand-grip strength, SPPB, TUG, Short FES-I, GDS, a frailty assessment, and fall history for the prior year.

The dataset is **not included in this repository**. Download it before running the notebook.

### Running in Colab

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1y1Io68hIXozFJzBb_pYTswfkoq5i3nXb?usp=sharing)

Run this in a Colab cell to fetch and unpack the data directly into the session (faster than uploading from your machine):

```
!wget -O GSTRIDE_database.zip "https://zenodo.org/records/8003441/files/GSTRIDE_database.zip?download=1"
!md5sum GSTRIDE_database.zip    # expected: 47318e46265b391a039007b3436bf834
!unzip -q GSTRIDE_database.zip  # ~1.4 GB zipped, ~3.3 GB unpacked
```

Colab's local storage is cleared when the runtime resets, so re-run this cell after a reset (or copy the unpacked folder to Google Drive).
## Project Decision: Go. Ready to move ahead with this topic and dataset

## [Team Plan](PLAN.md)
[Dataset Summary](dataset-summary.png)
[Stride Speed/Length](stride-speed-length.png)
