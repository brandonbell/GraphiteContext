GraphiteContext
===============

Like the GangliaContext for Hadoop, sends metrics to Graphite

Compile:

$ jar -cf GraphiteContext.jar -C org/ .

Installation:

In your hadoop-env.sh file (usually in /etc/hadoop/conf/), add the location of the GraphiteContext.jar file into the HADOOP_CLASSPATH

example: export HADOOP_CLASSPATH="/home/brandon/GraphiteContext.jar"

Configuration:

In your hadoop-metrics.properties file, add the following for all metrics

mapred.class=org.apache.hadoop.metrics.graphite.GraphiteContext
mapred.period=60
mapred.serverName=<Your Graphite Server>
mapred.port=2013
jvm.class=org.apache.hadoop.metrics.graphite.GraphiteContext
jvm.period=60
jvm.serverName=<Your Graphite Server>
jvm.port=2013
dfs.class=org.apache.hadoop.metrics.graphite.GraphiteContext
dfs.period=60
dfs.serverName=<Your Graphite Server>
dfs.port=2013
ugi.class=org.apache.hadoop.metrics.graphite.GraphiteContext
ugi.period=60
ugi.serverName=<Your Graphite Server>
ugi.port=2013

<metric>.path=<path> can be used to specify the path in Graphite. Defaults to Platform.Hadoop

Restart Daemons:

$sudo /etc/init.d/hadoop-tasktracker restart
$sudo /etc/init.d/hadoop-tasktracker restart
$sudo /etc/init.d/hadoop-tasktracker restart
$sudo /etc/init.d/hadoop-tasktracker restart
