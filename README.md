# Analysing billion-objects catalogue interactively: Apach Spark for physicists

This repository contains supplementary material for arXiv:[1807.03078](https://arxiv.org/abs/1807.03078).

## How to run the notebook

You must have [Apache Spark](http://spark.apache.org/) and [Jupyter notebook](https://jupyter.org/) installed on your machine or your cluster. 

### On a local machine

```bash
PACK="com.github.astrolabsoftware:spark-fits_2.11:0.7.2"
PYSPARK_DRIVER_PYTHON_OPTS="jupyter-notebook" pyspark \
     --master local[*] \
     --packages $PACK 
```

### On a cluster

Standalone mode:

```bash
PACK="com.github.astrolabsoftware:spark-fits_2.11:0.7.2"
PYSPARK_DRIVER_PYTHON_OPTS="jupyter-notebook --debug --no-browser --port=$PORT1" pyspark \
     --master $SPARKURL \
     --packages $PACK \
     --driver-memory $MEMDRIVER --executor-memory $MEMEXEC --executor-cores $EXECCORES --total-executor-cores $TOTALCORES
```

### DESC members: working at NERSC

Source your DESC environement. Then go to the Jupyter Lab web [interface](https://jupyter-dev.nersc.gov/), and execute the notebook with the desc-pyspark kernel.