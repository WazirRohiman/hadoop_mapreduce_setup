Download Hadoop using curl
```
curl https://dlcdn.apache.org/hadoop/common/hadoop-3.2.3/hadoop-3.2.3.tar.gz --output hadoop-3.2.3.tar.gz
```

Extract the tar file in the current directory
```
tar -xvf hadoop-3.2.3.tar.gz
```

Navigate to Hadoop-3.2.3 directory
```
cd hadoop-3.2.3
```

To check if it is set up use the hadoop command below. A usage documenation for the Hadoop script will be displayed
```
bin/hadoop
```

In this example, we will use the data.txt file 
```
curl https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-BD0225EN-SkillsNetwork/labs/data/data.txt --output data.txt
```

Run the Map reduce application for wordcount on data.txt and store the output in /user/root/output
```
bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-3.2.3.jar wordcount data.txt output
```

Use ```ls``` command to see the output file n /user/root/output
```
ls output
```
You will see the following output from the terminla
```
part-r-00000  _SUCCESS
``` 
Indicating that the wordcount has completed.

Use the ```cat``` command to read the wordcount output
```
cat output/part-r-00000
```

The diagram below shows how the MapReduce wordcount works

![image](https://user-images.githubusercontent.com/13661373/216816908-9cedcd44-2911-4ad6-bfd7-166f668ade42.png)
