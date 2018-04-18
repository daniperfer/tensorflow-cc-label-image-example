# TensorFlow C++ label image example

Ubuntu 14.04+

## Data download

First, download inception_v3 model:

```  
$ cd data
$ bash tensorflow_example_download_data.sh
```

## How to build

Create a `build` folder and compile with cmake.

From root folder (`tensorflow_cc_label_image_example` folder):

```  
$ mkdir build & cd build
$ cmake ..
$ make
```

## Usage

From `build` folder, run:

```  
$ ./tensorflow_cc_label_image_example
```

Or, alternatively:

```  
$ ./tensorflow_cc_label_image_example --image="../data/grace_hopper.jpg" --graph="../data/inception_v3_2016_08_28_frozen.pb" --labels="../data/imagenet_slim_labels.txt"
```