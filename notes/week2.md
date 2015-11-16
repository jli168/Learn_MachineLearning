
#### Octave notes

##### 1. load a function from a file
*	create a function in a file, 
*	move the octave path to that file's folder, so that octave can find the function
*	`source "filename"` to load the function [ref 1](http://www.gnu.org/software/octave/doc/interpreter/Script-Files.html), [ref 2](http://stackoverflow.com/questions/2068599/octave-load-many-functions-from-single-file)

##### 2. Handle submit error 'Submission failed: unexpected error: urlread: HTTP response code said error'
*	Solution: look at Jacob Middag's answer in [this page](https://learner.coursera.help/hc/en-us/community/posts/204693179-linear-regression-submit-error) for the solution :) 


##### 3. Make `plot` work on Mac!
*	Check out [this tutorial](http://jatinganhotra.com/blog/2014/01/21/installing-octave-on-os-x-10-dot-9-mavericks/) to solve problems
*	I solved mine by these two lines: 
	
	```
	$ brew uninstall gnuplot
	$ brew install gnuplot --with-x
	```