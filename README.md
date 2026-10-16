# How Is Gait-Derived Endurance Related to Falls?

BMEN 600, Group 9, University of Calgary: Ahmed Osman, Hanna Musnicka, Sheikh Falah Sheikh Hasan, Rubbina Bhatti

## Research Question

Does the rate at which gait speed declines over one sustained walk (gait-derived endurance) relate to fall history and to self-reported exhaustion (the "low energy" item of Fried's frailty phenotype)? Does it add information beyond walk duration, average gait speed, the Timed Up and Go (TUG) and the Short Physical Performance Battery (SPPB)?

We define gait-derived endurance as the within-walk decline in stride-level gait parameters (speed, stride length, cadence) during a walk of about 20 minutes recorded with a foot-mounted IMU.

## Dataset

**GSTRIDE** v1.0 (García-Villamil Neira et al.), Zenodo: [10.5281/zenodo.8003441](https://doi.org/10.5281/zenodo.8003441), licensed CC BY 4.0. It is described in García-de-Villa et al., *Scientific Data* 10, 566 (2023), [10.1038/s41597-023-02428-0](https://doi.org/10.1038/s41597-023-02428-0).

163 older adults (45 men, 118 women, aged 70–98), 86 of whom reported a fall in the past year. Each participant has one walking test recorded with a foot-mounted IMU (mean duration 21.4 ± 7.1 min) plus a clinical battery: 4-m gait speed, hand-grip strength, SPPB, TUG, Short FES-I, GDS, a frailty assessment, and fall history for the prior year.

**Access.** The dataset is free to download from Zenodo with no account: one zip file, `GSTRIDE_database.zip` (1.4 GB zipped, 3.3 GB unpacked, MD5 `47318e46265b391a039007b3436bf834`). Unzipping it creates a `GSTRIDE_database/` folder, which must sit next to the notebook.

**Why it is not in this repository.** The files are too large for GitHub. The license allows redistribution, but the data are participant-level clinical and gait records, so we leave them on Zenodo and link to the original source. We report results only in aggregate.

## Files

| File | Contents |
|---|---|
| `README.md` | This page |
| [`PLAN.md`](PLAN.md) | Team roles and timeline |
| [`GStride_Exploration.ipynb`](GStride_Exploration.ipynb) | Current progress check. Loads the clinical register and the per-stride gait files, checks which participants have which files, cleans the register, and produces Table 1 (cohort characteristics), figures of the cohort and clinical measures, a check of who could not answer the exhaustion item, and the full per-stride series for one participant (V001) |
| [`dataset-summary.png`](dataset-summary.png) | Cohort composition from the notebook: age band by sex, BMI, 4-m gait speed, test setting, walking surface, recording device |
| [`stride-speed-length.png`](stride-speed-length.png) | Figure 1 of the midterm plan: V001's speed, stride length and stride time across the walk, with the 3 s pause threshold |

`GSTRIDE_database/` (the downloaded data) is not tracked.

## Software

- **Platform:** Google Colab, or Jupyter on your own machine
- **Language:** Python 3 (the saved outputs came from Python 3.10)
- **Packages:** numpy, pandas, matplotlib, scipy. All four come preinstalled on Colab. The saved outputs used numpy 2.2.6, pandas 2.3.3 and matplotlib 3.10.9.

## Running the Progress Check

### In Google Colab

1. Open the notebook: [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ahmadMfouad/BMEN600-GROUP9/blob/main/GStride_Exploration.ipynb)
2. Add a code cell at the top and paste in the lines below. They download the data and unpack it into the session, which is faster than uploading it from your machine.

   ```
   !wget -O GSTRIDE_database.zip "https://zenodo.org/records/8003441/files/GSTRIDE_database.zip?download=1"
   !md5sum GSTRIDE_database.zip    # expected: 47318e46265b391a039007b3436bf834
   !unzip -q GSTRIDE_database.zip  # ~1.4 GB zipped, ~3.3 GB unpacked
   ```

3. Choose **Runtime → Run all**.

Colab clears its local storage when the runtime resets. After a reset, run the download cell again, or copy the unpacked folder to Google Drive.

### On Your Own Machine

```
git clone https://github.com/ahmadMfouad/BMEN600-GROUP9.git
cd BMEN600-GROUP9
curl -L -o GSTRIDE_database.zip "https://zenodo.org/records/8003441/files/GSTRIDE_database.zip?download=1"
md5sum GSTRIDE_database.zip    # on macOS: md5 GSTRIDE_database.zip
unzip -q GSTRIDE_database.zip
pip install numpy pandas matplotlib scipy jupyter
jupyter notebook GStride_Exploration.ipynb
```

Pick the default Python 3 kernel if Jupyter asks for one, then choose **Run → Run All Cells**.

If `GSTRIDE_database/` is not next to the notebook, the first code cell stops with an error. If it is there, the notebook prints 163 subjects in the register.
