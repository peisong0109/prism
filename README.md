# prism

prism ia a Probabilistic Symbolic Model Checker.

This tutorial will introduce you to the PRISM tool.

### 1. Download JDK/JRE
https://www.oracle.com/java/technologies/downloads/#java17

![image](https://github.com/peisong0109/prism/blob/main/screenshot/jdk.png)

### 2. Download and install PRISM
http://www.prismmodelchecker.org/download.php

![image](https://github.com/peisong0109/prism/blob/main/screenshot/prism.png)

### 3. Open PRISM 4.7 

Copy the following code:
```
dtmc
module die
	//local state
	s : [0..7] init 0;
	//value of the die
	d : [0..6] init 0 ;
	[]s=0 -> 0.5 : (s'=1) + 0.5 :(s'=2);
	[]s=1 -> 0.5 : (s'=3) + 0.5 :(s'=4);
	[]s=2 -> 0.5 : (s'=5) + 0.5 :(s'=6);
	[]s=3 -> 0.5 : (s'=1) + 0.5 :(s'=7)&(d'=1);
	[]s=4 -> 0.5 : (s'=7)&(d'=2) + 0.5 :(s'=7)&(d'=3);
	[]s=5 -> 0.5 : (s'=7)&(d'=4) + 0.5 :(s'=7)&(d'=5);
	[]s=6 -> 0.5 : (s'=2) + 0.5 :(s'=7)&(d'=6);
	[]s=7 -> (s'=7);
endmodule
```

![image](https://github.com/peisong0109/prism/blob/main/screenshot/example.png)

Choose Properties, double click the blank area and type:

![image](https://github.com/peisong0109/prism/blob/main/screenshot/property.png)

```
P=? [F s=7 & d=6]
```

![image](https://github.com/peisong0109/prism/blob/main/screenshot/editor.png)

Choose the newly added property and choose verify (or press F5), the details of this property will be shown.

![image](https://github.com/peisong0109/prism/blob/main/screenshot/details.png)

More functions and recently developed features about PRISM can be found at:

http://www.prismmodelchecker.org/manual/

### 4. Case study

