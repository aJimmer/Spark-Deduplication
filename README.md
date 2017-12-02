# Connect to EMR instance

* Please SSH into the EMR master node using the `Hadoop.pem` file provided.

* **For MAC/Linux:** `ssh -i Hadoop.pem hadoop@ec2-54-183-89-163.us-west-1.compute.amazonaws.com`

* **For Windows:** 
1. Download PuTTY.exe to your computer from:
2. http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html
3. Start PuTTY.
4. In the Category list, click Session.
5. In the Host Name field, type hadoop@ec2-54-183-89-163.us-west-1.compute.amazonaws.com
6. In the Category list, expand Connection > SSH, and then click Auth.
7. For Private key file for authentication, click Browse and select the private key file (Hadoop.pem) used to launch the cluster.
8. Click Open.
9. Click Yes to dismiss the security alert.

## Go to

`cd /home/hadoop/project/Spark-Deduplication`

## Run Application

`./run.sh`

## After successfull execution of script run following commands to move data from hdfs to local system

`hdfs dfs -get /ded_output /home/hadoop/project/Spark-Deduplication`

`hdfs dfs -get /ded_input /home/hadoop/project/Spark-Deduplication`

## Check inout data

`cat ded_input/ded.txt`

## Check output data

`cat ded_output/part-00000`
