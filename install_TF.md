# Install CUDA 10 & cuDNN & TensorRT and test installation

        python3 -m venv ml
        source ml/bin/activate


        (ml) pip install tf-nightly-gpu # ONLY nightly builds supports CUDA 10 (as of 20190109)

        (ml) pip install h5py

        sudo apt install python-pydot python-pydot-ng graphviz

        (ml) pip install keras

        python -c 'import keras; print(keras.__version__)' # show Keras version

# Noise2Noise (TensorFlow noise reduction neural network)

This should run through roughly 50K images and output a file called `datasets/imagenet_val_raw.tfrecords`.
        
        python dataset_tool_tf.py --input-dir "imagenet/ILSVRC2012_img_val" --out=datasets/imagenet_val_raw.tfrecords

