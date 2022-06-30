# End-to-end-learning-for-self-driving-cars
<h3><b>Approach-01  : Self Driving Car (End-to-End CNN/Dave-2)</b></h3>
<img src="https://camo.githubusercontent.com/7b34f1caec74578997546bd706e8dc1e76a302d905567bfc22657e3e009f385f/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f3836382f302a37645265715158456c6e6548425755722e6a7067">

<ul>
  <li> I have trained a convolutional neural network (CNN) to map raw pixels from a single front-facing camera directly to steering commands.The CNN approach is especially powerful in image recognition tasks because the convolution operation captures the 2D nature of images.This powerful end-to-end approach means that with minimum training data from humans, the system learns to steer, with or without lane markings, on both local roads and highways. The system can also operate in areas with unclear visual guidance such as parking lots or unpaved roads. </li>
 <li>The system is trained to automatically learn the internal representations of necessary processing steps, such as detecting useful road features, with only the human steering angle as the training signal. We do not need to explicitly trained it to detect, for example, the outline of roads.</li>
  <li>End-to-end learning leads to better performance and smaller systems. Better performance results because the internal components self-optimize to maximize overall system performance, instead of optimizing human-selected intermediate criteria, e. g., lane detection.</li> 
  </ul>
  <ul>
  <li>Training data was collected by driving on a wide variety of roads and in a diverse set of lighting and weather conditions.
    To download training data  go to the <a target="_blank" href="https://github.com/SullyChen/Autopilot-TensorFlow">link</a> . 
  </li>
  </ul>
  <h3><b>System requirements </b></h3>
  <ul> <li> pip3 install scipy</li>
  <li> pip3 install tensorflow</li>
  <li>pip3 install opencv </li>
  <li>pip3 install numpy</li>
  </ul>
  <h3><b>How to use </b> </h3>
  <ul> <li>  python3 train.py : to train the model </li>
  <li>python3 run.py : to run the model on a live webcam feed </li>
  
  <li>python3 run_dataset.py : to run the model on the dataset </li>
  <li>To visualize training using Tensorboard use tensorboard --logdir=./logs, then open http://0.0.0.0:6006/ into your web browser.</li>
  </ul>
  <h3><b>Demo</b></h3>
  <img src="https://github.com/adityaguptai/Self-Driving-Car-/raw/master/self_driving_car_gif.gif">

<h3><b> Model Training and Evaluation</b></h3>
<ul>
<li>I've splitted the data into 80% training set and 20% validation set to measure the performance after each epoch.</li>
<li>I used Mean Squared Error (MSE) as a loss function to measure how close the model predicts to the given steering angle for each input frame.</li>
<li>I used the Adaptive Moment Estimation (Adam) Algorithm minimize to the loss function. Adam is an optimization algorithm introduced by D. Kingma and J. Lei Ba in a 2015 paper named Adam: A Method for Stochastic Optimization. Adam algorithm computes adaptive learning rates for each parameter. In addition to storing an exponentially decaying average of past squared gradients like Adadelta and RMSprop algorithms, Adam also keeps an exponentially decaying average of past gradients mtmt, similar to momentum algorithm, which in turn produce better results.</li>
<li>I used ModelCheckpoint from Keras to check the validation loss after each epoch and save the model only if the validation loss reduced.</li>

