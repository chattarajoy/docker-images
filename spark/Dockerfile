FROM mesosphere/spark:2.10.0-2.4.5-scala-2.11-hadoop-2.9

 RUN   apt-get -y update \                                                                                                                                                                                                                        
  &&   apt-get -y install ca-certificates wget \                                                                                                                                                                                                      
  &&   update-ca-certificates  

ENV SPARK_HOME=/opt/spark
  
RUN mkdir -p /tmp && \
 cd /tmp && \
 wget https://repo1.maven.org/maven2/org/apache/hadoop/hadoop-aws/2.9.2/hadoop-aws-2.9.2.jar && \
 wget https://repo1.maven.org/maven2/com/amazonaws/aws-java-sdk-bundle/1.11.199/aws-java-sdk-bundle-1.11.199.jar && \
 wget https://repo1.maven.org/maven2/org/apache/commons/commons-lang3/3.4/commons-lang3-3.4.jar && \
 wget https://repo1.maven.org/maven2/org/apache/spark/spark-hive_2.12/2.4.5/spark-hive_2.12-2.4.5.jar

RUN rm -rf $SPARK_HOME/jars/kubernetes-client-*.jar
ADD https://repo1.maven.org/maven2/io/fabric8/kubernetes-client/4.4.2/kubernetes-client-4.4.2.jar $SPARK_HOME/jars

RUN mv /tmp/*.jar $SPARK_HOME/jars
