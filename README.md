 <img src="https://github.com/54LiNKeR/54LiNKeR.github.io/blob/master/shots/LiNKeR.png" width="35%">
 
 # Getting-Started-With-DeepLearning4j-on-Android

Hi Reader, it is great you are here again! this is just a quick follow up to my previous article on getting started with deeplearning4j. So with the previous article I assume you must have been able to train a model and you would like to have that model run live within your android application.

## Quick Start

> **GRADLE**

```xml
    compile 'org.deeplearning4j:deeplearning4j-nn:1.0.0-beta'
    compile 'org.nd4j:nd4j-native:1.0.0-beta'
    compile 'org.nd4j:nd4j-native:1.0.0-beta:android-x86'
    compile 'org.nd4j:nd4j-native:1.0.0-beta:android-arm'
```

## Slow Start

The next thing to do would be to have your saved model stored inside your resources directory in a raw folder(cr8 one if it does not exist).
    
<img src="shots/raw_folder_demo.png" width="49%">
    
As you can see above the name of my model is **`stupidAI.wise`**. Inorder to load the model we have to get dirty with some little Java

> **JAVA**

```java   
           MultiLayerNetwork network;
            try {
                InputStream inputStream = getResources().openRawResource(R.raw.stupidAI);
                network = ModelSerializer.restoreMultiLayerNetwork(inputStream);
            } catch (IOException e) {
                e.printStackTrace();
            }         
```
KabooOOom!!! we have the network-model live now you can do what ever you want. Just like in the previous tutorial   
So say you have built a neural network to figure out how to read your girlfriend's facial expressions, so you know 
when she's in the mood or not(mood for some ice-cream just incase you spiked off).So @ run-time you are most likely getting
images from the camera as a Bitmap. So having trained the model on your PC, cloud or you're implementing a trained network-model
and you would like to pass your Bitmap frames through the network to determine if shes in the mood or not. 
You could implement my [`BinTrasher`](https://github.com/54LiNKeR/BinTrasher) library to quickly scale the Bitmap to an INDArray and feed it to the network. e.g.

> if your reading this @tm I am still working on this thread



    
