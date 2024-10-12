### Kaggle Public Baselines
* (1%) Simple baseline: 0.45797 (sample code)
* (1%) Medium baseline: 0.69747 (concat n frames, add layers)
* (1%) Strong baseline: 0.75028 (concat n, batchnorm, dropout, add layers)
* (1%) Boss baseline: 0.82324 (sequence-labeling(using RNN))

### 心得
DNN model勉強可以過strong baseline, 改用RNN後反而掉到Medium baseline, 也許是架構問題, 也許是相關的超參數調得太差

