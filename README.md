# Lithuanian parliamentary presence data

Here you can find Lithuanian parliamentary presence data. This data was
scrapped from the Lithuanian parliament website
<https://www.lrs.lt/sip/portal.show?p_r=35391&p_k=1> (at the time of writing
the site was available only in Lithuanian) on 2019-06-08.

The full data provides information whether a particular representative was
elected at the time and whether the representative was registered to vote on
specific agenda. We have aggregated the data on the daily level. We have
assumed that the representative was present if the representative registered to
vote at least once that day. We have encode presence as 1, absence as 0, data
is missing (empty) if the representative was not elected on the said day. The
aggregated data for all days available at the time of processing is made
available as `attendance-daily-abs.csv`. `attendance-daily-abs.csv` has both
header row (the dates) and index column (the representative ids).

`attendance-2008.csv` and `attendance-2012.csv` are the data files used for
analysis in [1].
They were obtained by doing some additional processing of
`attendance-daily-abs.csv`. Additional steps include:

* Subsetting the data based on the legislature.
* Merging attendance data. We have detected predecessors, who haven't finished
their term, and their successors, who were elected to replace them, and joined
their attendance records. So that we would have 141 attendance records with as
few missing data as possible.
* Replacing attendance records with missing data. We have replaced incomplete
records with random copies of complete records.

Unlike `attendance-daily-abs.csv` file `attendance-2008.csv` and
`attendance-2012.csv` files do not have neither header row, nor column row.
These files have exactly 141 rows, which are filled with 1 and 0.

The original data is available under
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) license. You are free
to use our aggregated data freely. Though references to [1] would be
appreciated.

## Reference

1. A. Kononovicius. *Noisy voter model for the anomalous diffusion of parliamentary presence*.
Journal of Statistical Mechanics 2020: 063405 (2020).
doi: [10.1088/1742-5468/ab8c39](https://doi.org/10.1088/1742-5468/ab8c39).
[arXiv:2001.01479 [physics.soc-ph]](https://arxiv.org/abs/2001.01479).
