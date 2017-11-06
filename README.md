# tensorflow-java
Tensorflow Java examples

## How To Install
You need to run the `jni.sh` to install the right Java bindings for your platform and the `download.sh` script that will download the `inception5` model in order to be ready to run a simple examples:

```bash
git clone https://github.com/loretoparisi/tensorflow-java.git \
cd tensorflow-java \
sh jni.sh \
sh download.sh \
```

## How to Run the Inception example
```bash
cd tensorflow-java
javac -cp lib/libtensorflow-1.4.0.jar LabelImage.java
java -cp lib/libtensorflow-1.4.0.jar:. -Djava.library.path=./jni LabelImage models/ images/example-400x288.jpg
```

## A simple Hello World example
Create a simple Java class with a main to be executable and import `org.tensorflow.TensorFlow`

```java
import org.tensorflow.TensorFlow;

public class TensorFlowExample {
  public static void main(String[] args) {
    System.out.println("TensorFlowExample using TensorFlow version: " +  TensorFlow.version());
  }
}
```

Save it and then from command line compile and run

```bash
cd tensorflow-java
javac -cp lib/libtensorflow-1.4.0.jar TensorFlowExample.java
java -cp lib/libtensorflow-1.4.0.jar:. -Djava.library.path=./jni TensorFlowExample
```

If you get the TensorFlow version as output it worked!

```bash
TensorFlowExample using TensorFlow version: 1.0.0-rc2
```

## Disclaimer
This example is provided as it is and it is based on the official Tensorflow Java JNI wrapper and example available [here](https://github.com/tensorflow/tensorflow/tree/master/tensorflow/java).
