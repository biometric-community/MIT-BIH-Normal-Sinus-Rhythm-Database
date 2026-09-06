# MIT-BIH Normal Sinus Rhythm Database (NSRDB)

[![License: ODC-By 1.0](https://img.shields.io/badge/License-ODC--By%201.0-green)](https://opendatacommons.org/licenses/by/1-0/)
[![Access: public](https://img.shields.io/badge/access-public-0e8a16.svg)](https://physionet.org/content/nsrdb/1.0.0/)

**MIT-BIH Normal Sinus Rhythm Database (NSRDB)** — long-term ECG recordings of subjects with no significant arrhythmias; PhysioNet open access.

- **Dataset repository**: https://github.com/biometric-community/MIT-BIH-Normal-Sinus-Rhythm-Database
- **Upstream source**: https://physionet.org/content/nsrdb/1.0.0/
- **DOI**: https://doi.org/10.13026/C2NK5R
- **Original format**: PhysioNet WFDB (`.dat` / `.hea` / `.atr`) under `data/`
- **License (data)**: [Open Data Commons Attribution License v1.0](https://opendatacommons.org/licenses/by/1-0/) (PhysioNet)
- **License (helpers / docs)**: CC BY 4.0 (see [`LICENSE`](LICENSE))

| Field | Value |
|-------|-------|
| Catalog id (tbiom) | `nsrdb` |
| Category | `physio` |
| Access | `public` |
| PhysioNet / WFDB slug | `nsrdb` |
| Upstream homepage | https://physionet.org/content/nsrdb/1.0.0/ |
| Paper alias | NSRDB (e.g. Abdeldayem & Bourlai, TBIOM 2019 spectral-correlation ECG ID) |

## TL;DR

- **Task**: normal-sinus ECG analysis / ECG identity benchmarking
- **Modality**: two-channel ECG (WFDB `.dat` / `.hea`) plus beat annotations
- **Platform**: MIT-BIH long-term ambulatory recordings
- **Real/Synthetic**: real
- **Subjects / records**: **18** long-term recordings
- **Sampling**: **128 Hz**
- **Citation**: see PhysioNet NSRDB page

## Download

- **This repository**: WFDB records under [`data/`](data/) (when populated).
- **Upstream**: https://physionet.org/content/nsrdb/1.0.0/
- **Helper script** (from tbiom monorepo root):

```bash
bash projects/datasets/scripts/download_nsrdb.sh
```

Preferred (after `pip install wfdb`):

```bash
python -c "import wfdb; wfdb.dl_database('nsrdb', r'projects/datasets/nsrdb/data')"
```

## Dataset structure

```text
nsrdb/
├── README.md
├── LICENSE
└── data/
    ├── RECORDS
    ├── ANNOTATORS
    ├── 16265.dat / .hea / .atr
    └── …
```

## Quick start

```python
import wfdb

rec = wfdb.rdrecord("data/16265")
ann = wfdb.rdann("data/16265", "atr")
print(rec.sig_name, rec.fs, rec.p_signal.shape, len(ann.sample))
```

## License

- **Data** (PhysioNet NSRDB): [ODC-By 1.0](https://opendatacommons.org/licenses/by/1-0/)
- **Helpers / docs** in this repository: [CC BY 4.0](LICENSE)

## Citation

Please cite the PhysioNet NSRDB publication and the PhysioNet resource itself when using these data. See https://physionet.org/content/nsrdb/1.0.0/ for the recommended citations.

## Contact

- Upstream / PhysioNet: https://physionet.org/content/nsrdb/1.0.0/
- This mirror: https://github.com/biometric-community/MIT-BIH-Normal-Sinus-Rhythm-Database
