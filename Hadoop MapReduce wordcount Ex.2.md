Here is a sample text file that can be use to test the Hadoop MapReduce workcount concept
```
Italy Venice
Italy Pizza
Pizza Pasta Gelato
```

Store the file in hadoop directory. In this case the txt file is called datasample.txt

Run the Map reduce application for wordcount on data.txt and store the output in /user/root/outputsample
```
bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-3.2.3.jar wordcount datasample.txt outputsample
```

Use ```ls``` command to see the outputsample file n /user/root/outputsample
```
outputsample
```

Use the following ```cat``` command to read the outputsample wordcount
```
cat output/part-r-00000
```

The result in the terminal will be as follows
```
Gelato  1
Italy   2
Pasta   1
Pizza   2
Venice  1
```

