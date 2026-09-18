# BMEN 600 Project
## Group 9
## Ahmed Osman, Hanna Musnicka, Sheikh Falah Sheikh Hasan, Rubbina Bhatti
## Where Three ECG Algorithms Disagree
### Three widely deployed clinical algorithms measured the same 21,799 ECGs, the measurements are public, and nobody has checked where they diverge.
### On which ECGs do established clinical ECG algorithms disagree, and what characterizes those recordings?
### https://physionet.org/content/ptb-xl-plus/1.0.0/
### Our biggest uncertainty is whether the algorithms disagree enough to be worth studying at all, since they may turn out to agree very closely. Related to that, the "doctor" labels may not all have been checked by a doctor, which would undercut the comparison. Beyond those two, with 21,000 ECGs even meaningless differences will look statistically significant, and any difference we find between men and women might really just come down to weaker signal strength rather than sex itself. Rows with missing data could be exactly the difficult cases we care about, the recordings date from 1989 to 1996 so the equipment is old, and someone may have already published this since I only checked briefly. We can resolve the two serious ones tonight by comparing QT measurements from two of the algorithms to see how far apart they actually are, and by checking how many records were genuinely validated by a human. If the gaps are tiny, or almost nothing was human-checked, we change the plan before committing.
