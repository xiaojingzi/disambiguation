Name Disambiguation in AMiner
============
This is implementation of our KDD'18 paper:

Yutao Zhang, Fanjin Zhang, Peiran Yao, and Jie Tang. Name Disambiguation in AMiner: Clustering, Maintenance, and Human in the Loop. In Proceedings of the Twenty-Forth ACM SIGKDD International Conference on Knowledge Discovery and Data Mining (KDD'18).

## Requirements
- Linux
- python 3
- install requirements via ```
pip install -r requirements.txt``` 

Note: Running this project will consume upwards of 10GB hard disk space. The data preparation will take several hours. You are recommended to run this project on a Linux server.

## Data
The data is currently located at 173 server /home/share/name-dis/data [**_TODO_**]. Please put the _data_ directory into project directory.

## How to run
```bash
cd $project_path
export PYTHONPATH="$project_path:$PYTHONPATH"
python3 scripts/preprocessing.py

# global model
python3 global_/gen_train_data.py
python3 global_/global_model.py
python3 global_/prepare_local_data.py

# local model
python3 local/gae/train.py

# estimate cluster size
python3 cluster_size/count.py
```
Note: Training data in this demo are smaller than what we used in the paper, so the performance (F1-score) will be a little bit lower than reported scores.