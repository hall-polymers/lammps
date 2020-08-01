This is the LAMMPS software package that includes a custom pair_style that has been applied in the following work:
* Brown, J. R.; Seo, Y.; Hall, L. M. *Physical Review Letters* **2018**, 120, 127801. [[link]](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.120.127801)
* Seo, Y.; Shen, K.-H.; Brown, J. R.; Hall, L. M. *Journal of the American Chemical Society* **2019**, 141, 18455–18466. [[link]](https://pubs.acs.org/doi/abs/10.1021/jacs.9b07227)
* Shen, K.-H.; Hall, L. M. *Macromolecules* **2020**, 53, 3655–3668. [[link]](https://pubs.acs.org/doi/abs/10.1021/acs.macromol.0c00216)

## pair_style bornsolv command

### Syntax
```
pair_style style args
```

* style = bornsolv
* args = list of arguments for a particular style

```
bornsolv args = cutoff
  cutoff = global cutoff for Lennard Jones interactions (distance units)
```


### Examples
```
pair_style bornsolv 5.0
pair_coeff 1 3* 4.0 1.0
pair_coeff 3* 3* 2.0 1.0
```

### Description
The bornsolv style compute the 1/r^4 Born solvation potential, given by

<a href="https://www.codecogs.com/eqnedit.php?latex=\large&space;E=S&space;[\left&space;(&space;\frac{\sigma}{r_{}}&space;\right&space;)^{4}-\left&space;(&space;\frac{\sigma}{r_{c}}&space;\right&space;)^{4}]" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\large&space;E=S&space;[\left&space;(&space;\frac{\sigma}{r_{}}&space;\right&space;)^{4}-\left&space;(&space;\frac{\sigma}{r_{c}}&space;\right&space;)^{4}]" title="\large E=S [\left ( \frac{\sigma}{r_{}} \right )^{4}-\left ( \frac{\sigma}{r_{c}} \right )^{4}]" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=r_{c}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?r_{c}" title="r_{c}" /></a> is the cutoff.

### Coefficients
The following coefficients must be defined for each pair of atoms types via the [pair_coeff](https://lammps.sandia.gov/doc/pair_coeff.html) command as in the examples above, or in the data file or restart files read by the [read_data](https://lammps.sandia.gov/doc/read_data.html) or [read_restart](https://lammps.sandia.gov/doc/read_restart.html) commands, or by mixing as described below:

* <a href="https://www.codecogs.com/eqnedit.php?latex=S" target="_blank"><img src="https://latex.codecogs.com/gif.latex?S" title="S" /></a> (energy units)
* <a href="https://www.codecogs.com/eqnedit.php?latex=\sigma" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\sigma" title="\sigma" /></a> (distance units)
* LJ cutoff (distance units)

Note that <a href="https://www.codecogs.com/eqnedit.php?latex=\sigma" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\sigma" title="\sigma" /></a>  is defined in the LJ formula as the zero-crossing distance for the potential, not as the energy minimum at <a href="https://www.codecogs.com/eqnedit.php?latex=2^{\frac{1}{6}}\sigma" target="_blank"><img src="https://latex.codecogs.com/gif.latex?2^{\frac{1}{6}}\sigma" title="2^{\frac{1}{6}}\sigma" /></a>.

The last coefficient is optional. If not specified, the global LJ cutoff specified in the pair_style command are used.

##### All other info for this pair style is the same as [pair_style lj/cut](https://lammps.sandia.gov/doc/pair_lj.html) such as info about speed packages, mixing, shift, table, tail correction, restart, rRESPA.


LAMMPS stands for Large-scale Atomic/Molecular Massively Parallel
Simulator.

Copyright (2003) Sandia Corporation.  Under the terms of Contract
DE-AC04-94AL85000 with Sandia Corporation, the U.S. Government retains
certain rights in this software.  This software is distributed under
the GNU General Public License.

----------------------------------------------------------------------

LAMMPS is a classical molecular dynamics simulation code designed to
run efficiently on parallel computers.  It was developed at Sandia
National Laboratories, a US Department of Energy facility, with
funding from the DOE.  It is an open-source code, distributed freely
under the terms of the GNU Public License (GPL).

The primary author of the code is Steve Plimpton, who can be emailed
at sjplimp@sandia.gov.  The LAMMPS WWW Site at lammps.sandia.gov has
more information about the code and its uses.

The LAMMPS distribution includes the following files and directories:

README			   this file
LICENSE			   the GNU General Public License (GPL)
bench			   benchmark problems
cmake			   CMake build system
doc			   documentation
examples		   simple test problems
lib			   libraries LAMMPS can be linked with
potentials		   interatomic potential files
python			   Python wrapper on LAMMPS as a library
src			   source files
tools			   pre- and post-processing tools

Point your browser at any of these files to get started:

http://lammps.sandia.gov/doc/Manual.html         the LAMMPS manual
http://lammps.sandia.gov/doc/Intro.html          hi-level introduction
http://lammps.sandia.gov/doc/Build.html          how to build LAMMPS
http://lammps.sandia.gov/doc/Run_head.html       how to run LAMMPS
http://lammps.sandia.gov/doc/Developer.pdf       LAMMPS developer guide

You can also create these doc pages locally:

% cd doc
% make html                # creates HTML pages in doc/html
% make pdf                 # creates Manual.pdf and Developer.pdf
