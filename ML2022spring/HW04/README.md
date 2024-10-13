### HW04 Speaker Identification

- Baselines:
  - Easy: Run sample code and know how to use transformer.
  - Medium: Know how to adjust parameters of transformer.
  - Strong: Construct [conformer](https://arxiv.org/abs/2005.08100) which is a variety of transformer. 
  - Boss: Implement [Self-Attention Pooling](https://arxiv.org/pdf/2008.01077v1.pdf) & [Additive Margin Softmax]

```
Simple : 0.66025
Medium : 0.81750 Modify the parameters of the transformer modules in the sample code.
Strong : 0.88500 Conformer
```

其他實作, Self-Attention Pooling, Additive Margin Softmax, learning rate scheduler

### 心得
Overfitting很嚴重, trainset ratio=0.95, 或是L2 Regularization都沒什麼用, dropout=0.45也是極限了。
改成每跑6個epochs重新resplit dataset有好一點。

Model置換成Comformer後, performance有提升, `Self-Attention Pooling` 和 `Additive Margin Softmax` 倒是沒啥有提升。
跑15000 steps就差不多無法提升performance了。另外valid_steps=4000, 原先2000次有點頻繁。
