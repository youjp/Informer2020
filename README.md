# Informer: Beyond Efficient Transformer for Long Sequence Time-Series Forecasting
![Python 3.6](https://img.shields.io/badge/python-3.6-green.svg?style=plastic)
![PyTorch 1.2](https://img.shields.io/badge/PyTorch%20-%23EE4C2C.svg?style=plastic)
![cuDNN 7.3.1](https://img.shields.io/badge/cudnn-7.3.1-green.svg?style=plastic)
![License CC BY-NC-SA](https://img.shields.io/badge/license-CC_BY--NC--SA--green.svg?style=plastic)

This is the origin Pytorch implementation of Informer in the following paper: 
[Informer: Beyond Efficient Transformer for Long Sequence Time-Series Forecasting](https://arxiv.org/abs/2012.07436). Special thanks to `Jieqi Peng`@[cookieminions](https://github.com/cookieminions) for building this repo.

<p align="center">
<img src=".\img\informer.png" height = "360" alt="" align=center />
<br><br>
<b>Figure 1.</b> The architecture of Informer.
</p>

## Requeirements

- Python 3.6
- matplotlib == 3.1.1
- numpy == 1.17.3
- pandas == 0.25.1
- scikit_learn == 0.21.3
- torch == 1.2.0

Dependencies can be installed using the following command:
```bash
pip install -r requirements.txt
```

## Data

The ETT dataset used in the paper can be download in the repo [ETDataset](https://github.com/zhouhaoyi/ETDataset).
The required data files should be put into `data/ETT/` folder. A demo slice of the ETT data is illustrated in the following figure. Note that the input of each dataset is zero-mean normalized in this implementation.

<p align="center">
<img src="./img/data.png" height = "168" alt="" align=center />
<br><br>
<b>Figure 2.</b> A demo of the ETT data.
</p>


## Usage
Commands for training and testing the model with *ProbSparse* self-attention on Dataset ETTh1, ETTh2 and ETTm1 respectively:

```bash
# ETTh1
python -u main_informer.py --model informer --data ETTh1 --attn prob

# ETTh2
python -u main_informer.py --model informer --data ETTh2 --attn prob

# ETTm1
python -u main_informer.py --model informer --data ETTm1 --attn prob
```

More parameter information please refer to `main_informer.py`.


## Results

<p align="center">
<img src="./img/result_univariate.png" height = "300" alt="" align=center />
<br><br>
<b>Figure 3.</b> Univariate forecasting results.
</p>

<p align="center">
<img src="./img/result_multivariate.png" height = "250" alt="" align=center />
<br><br>
<b>Figure 4.</b> Multivariate forecasting results.
</p>


## Citation

If you find this repository useful in your research, please cite the following paper:

```
@inproceedings{haoyietal-informer-2021,
  author    = {Haoyi Zhou and
               Shanghang Zhang and
               Jieqi Peng and
               Shuai Zhang and
               Jianxin Li and
               Hui Xiong and
               Wancai Zhang},
  title     = {Informer: Beyond Efficient Transformer for Long Sequence Time-Series Forecasting},
  booktitle = {The Thirty-Fifth {AAAI} Conference on Artificial Intelligence, {AAAI} 2021},
  pages     = {online},
  publisher = {{AAAI} Press},
  year      = {2021},
}
```
