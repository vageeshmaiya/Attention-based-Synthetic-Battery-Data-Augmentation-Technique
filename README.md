# Attention-based-Synthetic-Battery-Data-Augmentation-Technique

## Get started
This project has been executed via google colab.


#### Steps To Follow:

1. Download the code as a zip file and extract the contents.

2. Create a new folder in google drive and upload the extracted contents into it.

3. The code to be executed in google colab: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1zAZ_TRzqYrBMC7ytMzo9DJClzE1I8rs1#scrollTo=JgRskn6_EIw-)

4. Make the necessary changes mentioned in the code to get the result.
 
5. The datsasets used can be found in the `informer_model/ETDataset-main/ETT-small` folder. Any new dataset to be used should be uploaded in the mentioned folder.
 
6. All changes pertaining to prediction length, dataset etc can be done in `main_informer.py` script. 

7. The dataset can be changed in `main_informer.py` in `data parser` under `Battery` (The name of the csv file used should be mentioned under the `data` parameter. The target parameter can be varied under the parameter `T`).


## Usage

To train and evaluate the Informer model on a dataset the following command is used in the google colab notebook :

```train & evaluate
!python -u main_informer.py --model informer --data Battery --train_epochs 4 --attn prob --freq s --features S 
```
The detailed descriptions about the arguments are as following:
| Parameter name | Description of parameter |
| --- | --- |
| model | The model used in the experiment. This can be set to `informer`, `informerstack` |
| data | The dataset name |
| train_epochs | The number of epochs the code has to run for (defaults to 6) |
| attn | Attention used in encoder (defaults to `prob`). This can be set to `prob` (informer), `full` (transformer) |
| freq | Freq for time features encoding (defaults to `h`). This can be set to `s`,`t`,`h`,`d`,`b`,`w`,`m` (s:secondly, t:minutely, h:hourly, d:daily, b:business days, w:weekly, m:monthly |
| features | The forecasting task (defaults to `M`). This can be set to `M`,`S`,`MS` (M : multivariate predict multivariate, S : univariate predict univariate, MS : multivariate predict univariate) |

On running the main code a `results` folder will be created where the output is stored.
