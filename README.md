# Connect to EMR instance

* Please SSH into the EMR master node using the `Hadoop.pem` file provided.

* **For MAC/Linux:** `ssh -i ~/Hadoop.pem hadoop@ec2-54-183-89-163.us-west-1.compute.amazonaws.com`

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

## Install git

`sudo yum install git`

`git --version`

## Install Maven

`sudo wget https://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo`

`sudo sed -i s/\$releasever/6/g /etc/yum.repos.d/epel-apache-maven.repo`

`sudo yum install -y apache-maven`

`mvn --version`


## Make project directory

`mkdir project`

`cd project`



## Clone repo

`git clone https://github.com/aJimmer/Spark-Deduplication.git`

## Go to

`cd /home/hadoop/project/Spark-Deduplication`



## Make shell script executable

`chmod a+x run.sh`

## Run Application

`./run.sh`

## After successfull execution of script run following command to move data from hdfs to local system

`hdfs dfs -get /ded_output /home/hadoop/project/Spark-Deduplication`

## Check output data
`cd ded_output`

`cat part-00000`
