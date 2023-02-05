Clone the following repo
```
git clone https://github.com/ibm-developer-skills-network/ooxwv-docker_hadoop.git
```

Go to the docker-hadoop directory
```
cd ooxwv-docker_hadoop
```

Compose the docker application
```
docker-compose up -d
```

**Side Note**: **Compose** is a tool that defines and run multi-contained docker applications. We use one YAML configuration file to configure and allows use to create and start all services.

Once the nodes are created, run namenode as a mounted drive on bash
```
docker exec -it namenode /bin/bash
```
-------------------------------------------------------------------------------------------------------------------------------------------------

Hadoop environment is configured by editing a set of configuration files:

    hadoop-env.sh Serves as a master file to configure YARN, HDFS, MapReduce, and Hadoop-related project settings.

    core-site.xml Defines HDFS and Hadoop core properties

    hdfs-site.xml Governs the location for storing node metadata, fsimage file and log file.

    mapred-site-xml Lists the parameters for MapReduce configuration.

    yarn-site.xml Defines settings relevant to YARN. It contains configurations for the Node Manager, Resource Manager, Containers, and Application Master.

For the docker image, these xml files have been configured already.

For the docker image we are using above these XML files have been configured already, which can be viewed using the following command from the directory ```/opt/hadoop-3.2.1/etc/hadoop/```

```
ls /opt/hadoop-3.2.1/etc/hadoop/*.xml
```

-----------------------------------------------------------------------------------------------------------------------------------------------------

##Create a file in the HDFS

Create a directory structure ```user/root/input```
```
hdfs dfs -mkdir -p /user/root/input
```

Copy all the Hadoop configuration files from ```/opt/hadoop-3.2.1/etc/hadoop/``` to the input directory above
```
hdfs dfs -put $HADOOP_HOME/etc/hadoop/*.xml /user/root/input
```

Download the following txt file into the current directory
```
curl https://raw.githubusercontent.com/ibm-developer-skills-network/ooxwv-docker_hadoop/master/SampleMapReduce.txt --output data.txt 
```

Copy the ```data.txt``` file into ```user/root``` directory
```
hdfs dfs -put data.txt /user/root/
```

View the content of the file copied into the HDFS using the command below
```
hdfs dfs -cat /user/root/data.txt
```






