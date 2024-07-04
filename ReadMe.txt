This is the data repository to "Patient Assignment Optimization with Time-Varying Demand and Flexible Physician Shifts: A System-of-Systems Perspective".

---------------------
In "7.1 Data Set", we provide:
(1) Time-based data (215 Days):
	Arrival rates (48 half-hour intervals per day)
	Average service times
	Average examination times
(2) Daily reentry probabilities:
	Column 1: Proportion of patients with no reentry
	Column 2 (p1): Proportion of patients with at least one reentry
	Note: Column 1 and Column 2 should sum to 1
	Column 3 (p2): Conditional probability of more than two reentries, given at least one reentry
	Unified reentry probability (p) is approximated by: 1/(1-p) = 1 + p1 * (1+p2)
(3) Lognormal distribution parameters for:
	Service times (mu and sigma of the underlying normal distribution)
	Examination times (mu and sigma of the underlying normal distribution)
Due to patient privacy protection, we do not provide raw records.

---------------------
In "7.2.1. Admission Control Problem", we provide:
(1) cases_indexes.csv
	Contains detailed data for each instance, including:
		mu (service rate)
		theta (examination rate)
		p (reentry probability)
		lam (arrival rate)
(2) single_manager_admission_control.xlsx
	Provides objective values for five admission control policies
	Used to replicate Figure 7 in the study
(3) Comparison figures
	Contains information related to Figure 8
	Includes data for instances other than instance 16

---------------------
In "7.2.2 Assignment Rate Optimization", we provide:
Text files containing the iteration process of objective values in optimizing assignment rates.
File naming convention:
	Format: "{Day}rate_opt{Mode}.txt"
	Day: Ranges from 153 to 215, representing the demand surge stage
	Mode: Indicates the optimization method used
		0: 'First accept'
		1: 'Mix of 8'
		2: 'Best accept'
		3: the proposed 'LAHC' algorithm

These files allow for tracking the objective values during optimization process for different days and methods.

---------------------
In "7.2.3 -- 7.4 Policies", we provide:
(1) JSON policy files, each including:
	Assignment rates
	Shift-based thresholds
(2) Specific policy file:
	File name: policy_record_h=1_MA1
	This is the recommended policy file
	It uses h=1 as handoff cost
	It implements the MA1 data-driven scheme
