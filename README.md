# StagingBench open data: AI virtual staging, same rooms in every tool

Scores and measurements from the public StagingBench benchmark (https://stagingbench.org). Each real room photo (CC0 or public domain, see `photos-credits.json`) is staged by different AI virtual staging tools, then the staged image is aligned to the original and compared.

## Files
- `results.json`: the 12 tools shown on the site, with access terms, prices checked and per tool notes (same structure as https://stagingbench.org/data/results.json).
- `all-scores.json` and `scores.csv`: per tool and room measurements, taken from the published `NN-score.json` files. Keys: aligned architecture drift (0 to 100, lower is better), raw drift, alignment status, framing result.
- `photos-credits.json`: sources and licences of the input photographs.

## Method in short
SIFT keypoints with a ratio test and a RANSAC similarity transform align the staged image to the original. Framing passes when at least 97% of the original frame is visible with limited zoom and rotation. Architecture drift is edge based and measured over the top 65% of the frame. When alignment fails (too few inliers) the drift value is an unaligned fallback and should not be ranked with aligned scores. Full method: https://stagingbench.org/methodology.html

## Notes
- 120 tool and room pairs: 12 tools, 10 rooms. Staged images from third party tools are not included.
- MLS rules vary, and a label on the image is commonly required for virtual staging.

## Licence
Data and text: CC BY 4.0. Please credit "StagingBench (https://stagingbench.org)".
