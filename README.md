# fine-grained 对照实验结果 
====
在11.9日本质上共修改了之前代码的三个部分，分别是model部分，acc计算部分，以及dataset部分。之前代码使用的lr衰减方式是stepLR（每30个epoch）<br>
通过对照实验，发现之前的代码出现问题的部分是model和acc计算的部分，只改变之前代码的acc计算部分，测试精度从67%提升到74%<br>
在改变acc计算方式之后，model和lr衰减方式保持不变，改变dataset部分，改变前和改变后得到的精度分别为73.46%和72.82%，这可以说明最初的版本的dataset部分没有问题<br>
在改变acc计算方式之后，dataset和lr衰减方式保持不变，改变model部分，得到的结果为81.56%<br>
改变acc计算方式，改变dataset和model部分，将lr的衰减方式改为在每个epoch内余弦衰减，得到的结果为82.93%<br>
保持上一的设置不变，仅将lr改变为在每个batch内衰减，得到的结果为83.28%<br>
保持上一的设置不变，仅将lr的衰减方式改变为stepLR（每30个epoch），得到的结果为%<br>
结论： 
-------
之前代码出问题的部分在于acc的计算方式和model部分，
