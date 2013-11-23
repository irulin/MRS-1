MRS
===

MR Spectroscopy Analysis Code

This code will be used for the py4data working group.

## GitHub Repo

https://github.com/dlab-berkeley/MRS

## Sample data

Clone above repo, then:

    git annex init <name for your local repo>
    git annex get

You can also get this from http://pirsquared.org/mirror_data/test_v1_data.txt
(and you could find that via `git annex whereis test_v1_data.txt`).

## Tasks

 - Translate
   - Start with matplotlib, but bokeh or a d3 target could be fun
   - Could demo ipython notebook interactive widgets for threshold selection
 - Test

### Data Structure:

 - Single object
 - Headers as attributes (or header dict?)
 - On, Off as (lists of DataFrames) or one Panel each?

### Current code does:

 - Read file (spectra are in groups of on, off, diff)
   - In the test data, we have 16 replicates, so 48 spectra.
 - Identify NAA peak, check with user
 - Identify outliers
   - sort by variance and plot
   - ask user which to ignore
   - (may be possible to clean up rather than discarding entire scans)
 - Average on runs and off runs, take difference
 - Identify peaks in difference
   - Glx is peaks 1 and 2 (from right as shown)
   - GABA is the next ? Cluster
 - Find baseline using specific regions of the spectrum that we know shouldn't change
 - Calculate area between peak and baseline
 - Sum On + Off and find creatine peak
    - Separate regions are used as baseline
 - Ratio of GABA:Creatine, and perform 'adjustments' (determined by physicists)

