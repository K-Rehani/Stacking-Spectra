# Reproducibility notes

## Available example

The saved notebook contains a SPARCL query for 100 QSO records with:

- `data_release`: `SDSS-DR16`
- `redshift`: 0.6–1.1
- `ra`: 0–10 degrees
- `dec`: 0–10 degrees
- sorting: redshift

The notebook's final output prints 100 SPARCL `specid` values. The report describes this SDSS sample and a second BOSS DR16 sample. The current notebook only contains the SDSS query; it does not supply the BOSS query or a DESI EDR example.

## External inputs and service

The spectra are retrieved remotely through SPARCL. The notebook does not contain the spectral arrays as independent input files. A rerun depends on the remote service, its available records, and the client's behavior. The printed identifiers help identify the original sample, but do not freeze the returned spectrum arrays or the service state.

To make a future run auditable, record:

- query constraints and retrieval fields;
- the complete selected `specid` list as a data file or stable notebook output;
- run date, SPARCL server/client versions, and data release labels returned for every record;
- any server-authentication requirement, without committing credentials;
- the source of every redshift and extinction value; and
- hashes or archival locations for any locally saved input arrays, subject to data-service terms.

## Software information currently present

The notebook metadata records Python 3.10.13. Imports include `sparclclient`, NumPy, Astropy, Specutils, Matplotlib, pandas, and `extinction`; the notebook also imports Data Lab client modules. Exact installed versions are not captured, and there is no verified lockfile or dependency file. Do not treat this list as a tested installation recipe.

The notebook has saved plot outputs, but it was not rerun as part of the October 2026 review. A future test report should name the exact environment, sample, date, and commands used.

## Scope of current outputs

The saved plots show one arithmetic-mean stack and one purported weighted-mean stack for the SDSS sample. They do not establish the reported BOSS example, support across the three releases, uncertainty coverage, quantitative emission-line measurements, or AGN physical properties.
