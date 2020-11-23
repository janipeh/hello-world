## Complaint report

Affects release: deployed MVision Segmentation Service 1.1, release 1.1.1

### Identifying information

Date of complaint:

Clinic:

Auto-segmentation model or service in question: Breast, Abdomen-lung and Headneck

### Problem description

Saad Ullah Akram identified that there is a bug in mvworker release related to large scans (with predicted probability maps larger than 20x138x512x512) could crash mvworker such that no segmentations are produced.

### Steps to reproduce

Send a large scan to the system.

## Analysis and evaluation

Review, evaluation and risk analysis / Aleksi Nurmi 2020-07-07:

Scans of that size are typically not encountered in intended use, and the problem does contribute to use errors.

Safety related: no

Security related: no

Criticality: P1 – minor

Need to report:

## Investigation

Investigation by Aleksi Nurmi with technical input from Saad Ullah Akram, 2020-07-07.

### Technical cause

Indexing error in pre-processing code of mvworker.

### Released/similar products

No other released produces have this function.

### Other causes and contributing factors

None identified

### Decided actions

Communication to customer: 

To be fixed in release 1.1.2 of MVision Segmentation Service 1.1.

## Resolution and verification

### Correction

Fixed in #93, author Saad Ullah Akram.

### Testing for effectiveness and unintended side effects

Aleksi Nurmi / 2017-07-10:

Environment: Eclipse 15.6, RTViewer

Expected results: the system produced results on oys-headneck-100-0, known to fail in 1.1.1.

Actual results: a structure set was produced

### Verification

Covered by change plan for release 1.1.2.
