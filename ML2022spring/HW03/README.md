### HW3 CNN
有11種分類的Classifier, 大量GPU和IO計算, 建議跑在Kaggle

```
Simple : 0.50099
Medium : 0.73207 Training Augmentation + Train Longer
Strong : 0.81872 Training Augmentation + Model Design + Train Looonger (+
Cross Validation + Ensemble)
Boss : 0.88446 Training Augmentation + Model Design +Test Time
Augmentation + Train Looonger (+ Cross Validation + Ensemble) 
```
可以用[prechained models](https://pytorch.org/vision/stable/models.html#classification), 但不要用pre-trained weights, 沒用pre-trained weights, performance沒比較好, ex: AlexNet(epoch=60, best acc: 0.84018)

Training Augmentation有實作, Model Design部分參考了prechained models的source code, 主要是兩層FC layer裡面, 兩層dropput(0.5), 並且在CNN layer和FC layer間用了AdaptiveAvgPool2d, 雖然我不知道這用處。patience=8(early stopping)。


best acc 0.89586
```
[ Train | 077/080 ] loss = 0.36217, acc = 0.87582
[ Valid | 077/080 ] loss = 0.29520, acc = 0.89586 -> best
Best model found at epoch 76, saving model
```

Cross Validation + Ensemble沒有實作, 但有用把trainning set和 validation set合併切成5個folds(k-folds)

Advanced Data Augmentation: mixup - 改動不小, 沒實作

Test Time Augmentation - 沒實作

Residual Implementation, 參考了[Dive into Deep Learning Ch8.6.2. Residual Blocks](https://d2l.ai/chapter_convolutional-modern/resnet.html#residual-blocks), 這個版本可以跑到0.95292, 實際跑完整的test不知道會是多少

```
[ Train | 076/080 ] loss = 0.10231, acc = 0.96741
[ Valid | 076/080 ] loss = 0.16865, acc = 0.95292 -> best
Best model found at epoch 75, saving model
```

相關參考

* https://blog.csdn.net/weixin_42369818/article/details/123796214
* https://blog.csdn.net/weixin_43154149/article/details/123943748
* https://blog.csdn.net/weixin_39925939/article/details/133303484
