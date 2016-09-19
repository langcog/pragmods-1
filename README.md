pragmods
========

Code for pragmatics experiments on Mechanical Turk – used for Frank et al. (under review). "Rational speech act models of pragmatic reasoning in reference games." Results, models, and analyses are available here: [https://github.com/langcog/pragmods]().

## Specifics

Note that js files are partitioned into three files with distinct functionality. `pragmods_helper_functions_c1.js` contains simple functions, `pragmods_parameter_setter_c1.js` has parameter settings to recreate the different experiments, and `pragmods_control_flow_c1.js` actually runs the experiments.

## Known bugs

The end function had a *formatting* bug that Firefox and Internet Explorer were not properly reading. However, because this was compartmentalized in the code of pragmods_c1 and not before, the people with Firefox were probable unable to even start the HIT in previous versions.

And bug with Internet Explorer: getElementByName does not work as it does in every other browser... this in turn makes the check for the last button to fail no matter what.

## Old instructions on how to run experiments

Using [submitterator](https://github.com/danlassiter/Submiterator) 1.0.

Use command line to get to the path your pragmods file is saved in.

0) If necessary set the Java stuff:

`export JAVA_HOME=/Library/Java/Home`

1) Add to the experiment_timeline doc what you will do

2) change the variables in parameter_setter

3) change the variables in `settings_c1.txt`

4) Run the submitterator

`python submiterator.py settings_c1.txt`

5) Update the code online

```
### Updating All ### (or just part, if you want)
scp -r * SUNERID@cardinal.stanford.edu:/afs/ir/group/langcog/WWW/expts/pragmods
scp * SUNETID@cardinal.stanford.edu:/afs/ir/group/langcog/WWW/expts/pragmods
scp * nc07agom@cardinal.stanford.edu:/afs/ir/group/langcog/WWW/expts/pragmods

## If you only changed one file, then:
scp pragmods_parameter_setter_c1.js SUNETID@cardinal.stanford.edu:/afs/ir/group/langcog/WWW/expts/pragmods
```

6) Post the HIT

`sh pragmods_c1-postHIT.sh`

7) Retrieve the results

`sh pragmods_c1-getResults.sh`

8) Add to experiment timeline the info you get.

9) Take `pragmods_c1.results.tsv` and make a copy of it where you want it and rename it there with a good description
