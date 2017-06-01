# Statement of the problem

In an HPC compuer, if we wnat to check the progress of a run, we do: `qstat -u $USER`

When you make `qstat -f <JobID>`, among many other things, the following is printed in the terminal window:

```
Job Id: 4507181.cx1b
    Job_Name = calcite_I_FREQC
    Job_Owner = username@login-3-internal.cx1.hpc.ic.ac.uk
    resources_used.cpupercent = 9
    resources_used.cput = 00:00:03
    resources_used.mem = 21308kb
    resources_used.ncpus = 16
    resources_used.vmem = 665940kb
    resources_used.walltime = 05:08:06

...

    Output_Path = login-3-internal.cx1.hpc.ic.ac.uk:/work/username/BS-A/structu
	res_CRY14/Calcite_I/DISPERSI/lower_volumes_form_EOS_0.87_0.98_V_eq/110.
	485887/FREQCALC_on_SUPERCELL_Landau_SHRINK_6_6/SCANMODE_1__-20_20_0.4/4
	_displacement/CVOLOPT/Findsym/FREQCALC/calcite_I_FREQC.o4507181

...

```
For the moment, the only way of `cd` to the directory is by copying and pasting the 4 lines on `Output_Path` onto the command line, and "glue" all these 4 lines together.

This is often a waste of time.

It would be very useful to type `name_of_function <JobID>` and directly change directory where the job is running or about to finish.

# What is the function `goto`

`goto` is a function that allows to change to the directory where the job is running.

# Installation

* Add the lines of the function `goto` at the end of the `~/.bashrc` or `~/.profile`.
* Do `. ~/.bashrc` or `. ~/.profile` respectively.

# Usage

Type `goto <JobID>` and you will be directly redirected to the directory where the job is running or about to finish.


# Contributing

All contributions to improve this function or creating a more general script that would include more things for checking the status of the runs are very welcome.

* Have a look at GitHub's ["How to contribute"](https://guides.github.com/activities/contributing-to-open-source/#contributing).
* If you are familiar with `git`: fork this repository and submit a pull request.
* If you are not familiar with `git`: 

    * If something should be improved, open an issue here on GitHub
    * If you think a new feature would be nice, open an issue
    * If you need a feature for your project (i.e. within a certain time frame), contact the maintainer directly to discuss whether it can be implemented time.
  Then we'll open an issue.

