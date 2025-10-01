# Pyspark-With-Python


🔹 What is PySpark?
PySpark is the Python API for Apache Spark, a distributed computing framework used to process large-scale data efficiently.
If you’re dealing with gigabytes, terabytes, or petabytes of data, Spark makes it possible to process it quickly using clusters of machines instead of a single computer.

🔹 Why PySpark?
Speed: Spark processes data in memory, making it faster than traditional MapReduce.
Scalability: Can run on a laptop, a cluster, or the cloud.
Flexibility: APIs available in Python, Scala, Java, and R.
Libraries: Spark SQL, MLlib (Machine Learning), GraphX, Structured Streaming.

Spark Architecture (Simplified)
Driver: Coordinates the execution of jobs.
Cluster Manager: Manages resources.
Executors: Workers that process the data.
Driver Program  →  Cluster Manager  →  Executors
       (Coordinator)       (Resource Manager)     (Workers doing actual tasks)
Imagine you are organizing a wedding 🎉

Driver (Project Manager / Wedding Planner):
Plans all tasks (food, decoration, music).

Cluster Manager (HR/Coordinator):
Decides how many cooks, decorators, and musicians you can hire based on budget.

Worker Nodes (Teams):

Cooks (Executor 1) prepare food.

Decorators (Executor 2) decorate the hall.

Musicians (Executor 3) manage music.

The Driver (wedding planner) coordinates with Cluster Manager (HR) → who assigns tasks to actual Workers (teams) → and results come back as a successful wedding (final program output).

🔹 Diagram (Text-based)

                |       Driver          |  
                | (SparkContext, DAG)   |
                +-----------+-----------+
                            |
                            v
                +-----------------------+
                |   Cluster Manager     |  <-- Manages resources
                +-----------+-----------+
                            |
        -----------------------------------------------
        |                                             |
+---------------+                           +---------------+
|  Worker Node 1|                           | Worker Node 2 |
|   Executors   |                           |   Executors   |
|   (Tasks)     |                           |   (Tasks)     |
+---------------+                           +---------------+
🔹 First PySpark Program
from pyspark.sql import SparkSession
# Step 1: Start SparkSession
spark = SparkSession.builder \
    .appName("PySparkIntro") \
    .getOrCreate()
# Step 2: Create a simple DataFrame
df = spark.range(1, 6)
df.show()
Output:

+---+
| id|
+---+
|  1|
|  2|
|  3|
|  4|
|  5|
+---+
Key Takeaway
PySpark = Spark + Python API.

