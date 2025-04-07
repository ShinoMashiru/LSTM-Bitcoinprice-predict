# LSTM-Bitcoinprice-predict
实验室的一个小项目，比特币价格预测，持续完善更新中
## 使用说明
1. 数据预处理，运行data_process_resample.py,得到经过预处理和时间序列重采样得到的4个csv文件（重采样间隔分别为5min，10min，15min，60min）。
   请注意！！！！原始数据集文件名默认为'allfuture-trades.csv',如果测试时原始数据集文件名有差异，应当手动修改文件名或者在data_process_resample.py中修改filename参数。
   请注意！！！！原始数据集csv文件各列名默应当为instrument_name	trade_id	side	size	price	created_time，之前原始csv文件列名可能还有中文后缀，如果有请手动删除(之前原始数据集手动把中文后缀删了，原始列名忘了，预处理代码里没管，直接用的英文列名)

    ```bash
    python data_process_resample.py
    ```
    ```预处理后得到文件
   'data_for_train_5min.csv'
   'data_for_train_10min.csv'
   'data_for_train_15min.csv'
   'data_for_train_60min.csv'
    ```
2. LSTM模型预测，运行test.py,得到在4个不同重采样间隔下训练的模型（重采样间隔分别为5min，10min，15min，60min）预测结果，得到4个存有指标结果的txt文件，4个可视化图片
   ```模型pth文件
   '5min.pth'
   '10min.pth'
   '15min.pth'
   '20min.pth'
    ```
    ```bash
    python test.py
    ```
    ```4个存有指标结果的txt文件保存在
    'result_5min.txt'
    'result_10min.txt'
    'result_15min.txt'
    'result_60min.txt'
    ```
    ```4个可视化图片保存在
    '5minpredictions.png'
    '10minpredictions.png'
    '150minpredictions.png'
    '60minpredictions.png'
    ```
