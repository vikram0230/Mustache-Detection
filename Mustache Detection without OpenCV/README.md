# Model Analysis
### Trial 1 🔴

Use InceptionV3 with GlobalAveragePooling, Softmax layers

> Result: The model was slow in learning

### Trial 2 🔴

*Trail 1* + 1024 neurons relu layer

> Result: The model did not learn. No visible increase in accuracy

### Trail 3 🔴

*Trail 2* + 512 neurons relu layer

> Result: Very slow learning. The model might need more epochs, but limited by Computational power. Doubtful that model might overfit.

#### *Additional Trials*

  * Try 20 epochs - check if accuracy crosses 80%
  > Result: Slow learning with too many fluctuations in accuracy. Reached 76% accuracy on 20 epochs.

### Trial 4 🔴

*Trail 3* + 256 Relu Layer

Expectation: Model might learn more

> Result: Better performance than Trail 3 till 10 epochs. But overfits on 20 epochs. Lesser noise seen on validation accuracy

### Trial 5 🔴

*Trail 4* + 0.3 Dropout

> Expectation: Reduce overfitting

> Result: Model does not learn.

### Trial 6 🔴

Use a paramgrid

> Expectation: Costs more time and computational power.

> Result: Didn't work

### Trial 7 🟡

Train last 17 of Inception model + Trial 4

> Result: Better Performance. 79% validation accuracy on 8 epochs after which it overfits. Accuracy staggers

#### *Additional Trials*

* Increase dataset from 5000-1000 to 8000-2000 images

> Result: Learning is slow. Overfits

* Increase learning rate from 0.0001 to 0.001

> Result: Staggered learning after few epochs

**Inference: Training on last 17 layers works!**

### Trial 8 🔴

*Trail 4* + 1024 units Relu layer with 0.001 lr and 8000-2000 images

> Result : Better learning. Learning retarding after 6 epochs.

#### *Additional Trials*

* *Trail 8* + 1024 units Relu layer

> Result: Not too much overfitting. Can try on 20 epochs.

* *Trail 8.1* trained on last 17 layers of inception model.

> Result: Better Learning. Too much fluctuations in validation.

* *Trail 8.2* - 1024 units Relu layer

> Result: Overfits. Learning is slower

### Trial 9 🟡

*Trial 4* + training last 52 layers of inception

> Result: Better Learning. Too many fluctuations on validation.

### Trial 10 🟢

*Trial 1* + training last 52 layers of inception

> Result: Best Learning. Overfits after 7 epochs with 87.4% validation accuracy.

![Accuracy Graph](https://github.com/vikram0230/Mustache-Detection/blob/main/Mustache%20Detection%20without%20OpenCV/graphs/trial%2010-acc.png?raw=true)

#### *Additional Trials*

* *Trial 10* + 1024 relu layer

> Result: Learning is slow after 3 epochs. Reached an accuracy of 88.4% on validation

![Accuracy Graph](https://github.com/vikram0230/Mustache-Detection/blob/main/Mustache%20Detection%20without%20OpenCV/graphs/trial10.1-acc.png?raw=true)

### Additional Ideas

* Use Sigmoid output layer - Doesn't work

* Train the last few layers of Inception model - Worked🎉

## Annotation
🟢 - Currently working best

🟡 - Works but contains flaws

🔴 - Doesn't work to the expected level
