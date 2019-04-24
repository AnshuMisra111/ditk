# ConvKB: A Novel Embedding Model for Knowledge Base Completion Based on Convolutional Neural Network

This program provides the implementation of the CNN-based model ConvKB for the knowledge base completion task. ConvKB obtains new state-of-the-art results on two standard datasets: WN18RR and FB15k-237 as described in [the paper](http://www.aclweb.org/anthology/N18-2053):

        @InProceedings{Nguyen2018,
          author={Dai Quoc Nguyen and Tu Dinh Nguyen and Dat Quoc Nguyen and Dinh Phung},
          title={{A Novel Embedding Model for Knowledge Base Completion Based on Convolutional Neural Network}},
          booktitle={Proceedings of the 16th Annual Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies (NAACL-HLT)},
          year={2018},
          pages={327--333}
          }
  
Please cite the paper whenever ConvKB is used to produce published results or incorporated into other software. I would highly appreciate to have your bug reports, comments and suggestions about ConvKB. As a free open-source implementation, ConvKB is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. 

ConvKB is free for non-commercial use and distributed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA) License. 

<p align="center"> 
<img src="https://github.com/daiquocnguyen/ConvKB/blob/master/model.png" width="344" height="400">
</p>

## Note

Update a new initialization for WN18RR: MR:763, MRR:0.253 and Hits@10:56.7. Please check [our new NAACL2019 paper](https://arxiv.org/abs/1808.04122).

        $ python train.py --embedding_dim 100 --num_filters 400 --learning_rate 0.00005 --name WN18RR --num_epochs 101 --saveStep 100 --model_name wn18rr_400_3

## Usage

### Requirements
- Python 3
- Tensorflow >= 1.6

### Training
To run the program:

        python train.py --embedding_dim <int> --num_filters <int> --learning_rate <float> --name <dataset_name> [--useConstantInit] --model_name <name_of_saved_model>

**Required parameters:** 

`--embedding_dim`: Dimensionality of entity and relation embeddings.  

`--num_filters`: Number of filters.

`--learning_rate`: Initial learning rate.

`--name`: Dataset name (WN18RR or FB15k-237).

`--useConstantInit`: Initialize filters by [0.1, 0.1, -0.1]. Otherwise, initialize filters by a truncated normal distribution.

`--model_name`: Name of saved models.

**Optional parameters:** 

`--l2_reg_lambda`: L2 regularizaion lambda (Default: 0.001).
  
`--dropout_keep_prob`: Dropout keep probability (Default: 1.0).
  
`--num_epochs`: Number of training epochs (Default: 200).

`--run_folder`: Specify directory path to save trained models.

`--batch_size`: Batch size.


## Benchmarks
* WN18 / WN18RR
* FB15 / FB15k-237

## Evaluation Metrics
* MRR
* HITS@10


## Acknowledgments     

I would like to thank Denny Britz for implementing a CNN for text classification in TensorFlow.
