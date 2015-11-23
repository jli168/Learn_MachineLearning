
#### Octave notes

##### 1. load a function from a file
*	create a function in a file, 
*	move the octave path to that file's folder, so that octave can find the function
*	`source "filename"` to load the function [ref 1](http://www.gnu.org/software/octave/doc/interpreter/Script-Files.html), [ref 2](http://stackoverflow.com/questions/2068599/octave-load-many-functions-from-single-file)

##### 2. Handle submit error 'Submission failed: unexpected error: urlread: HTTP response code said error'
*	Solution: look at Jacob Middag's answer in [this page](https://learner.coursera.help/hc/en-us/community/posts/204693179-linear-regression-submit-error) for the solution :) 
*	Specificly, it means: 
        ```
	Jacob Middag September 09, 2015 05:02
	It seems that the conversion from ASCII to the hexadecimal escape the jsonlib uses is not working properly anymore in Octave 4.0. You can get it fixed by replacing
	
	str=[str str0(pos0(i)+1:pos(i)-1) sprintf('_0x%X_',str0(pos(i)))];
	by
	
	str=[str str0(pos0(i)+1:pos(i)-1) sprintf('_0x%X_',toascii(str0(pos(i))))];
	and
	
	str=sprintf('x0x%X_%s',char(str(1)),str(2:end));
	by
	
	str=sprintf('x0x%X_%s',toascii(str(1)),str(2:end));
	in loadjson.m and makeValidFieldName.m
        ```
*	You only need to do it once, because every week's code assignments need the same `lib` folder. So just copy it from the previous week's folder to the next one. Example:
	```
	cp week2/machine-learning-ex1/ex1/lib/makeValidFieldName.m week3/machine-learning-ex2/ex2/lib/jsonlab/week3/machine-learning-ex2/ex2/lib/makeValidFieldName.m
	cp week2/machine-learning-ex1/ex1/lib/jsonlab/loadjson.m week3/machine-learning-ex2/ex2/lib/jsonlab/loadjson.m
	```
        
##### 3. Make `plot` work on Mac!
*	Check out [this tutorial](http://jatinganhotra.com/blog/2014/01/21/installing-octave-on-os-x-10-dot-9-mavericks/) to solve problems
*	I solved mine by these two lines: 
	
	```
	$ brew uninstall gnuplot
	$ brew install gnuplot --with-x
	```
