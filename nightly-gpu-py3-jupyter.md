
# nvidia-docker tensorflow / gpu / py3 / jupyter

https://stackoverflow.com/questions/50702395/how-to-know-which-version-of-docker-image-is-behind-latest-tag

Created notebooks are saved locally in a docker volume
-u $(id -u):$(id -g) This lets you run the container by specifying your user's userid:

    docker volume create vc_notebooks

    nvidia-docker run -it --rm --name tensorflow -v vc_notebooks:/tf -p 8888:8888 tensorflow/tensorflow:nightly-gpu-py3-jupyter

    nvidia-docker run -u $(id -u):$(id -g) -it --rm --name tensorflow -v /home/fuxen/Desktop/tf:/tf -p 8888:8888 tensorflow/tensorflow:nightly-gpu-py3-jupyter

    (follow instructions)

    docker exec -i -t tensorflow /bin/bash
This image (tensorflow/tensorflow:nightly-gpu-py3-jupyter) does not support TensorRT


# ASUS 2080-Ti (GPU blower style) fan speed Ubuntu 18.04:
https://devtalk.nvidia.com/default/topic/1038856/linux/fan-control-ubuntu-18-04/

sudo gedit /usr/share/X11/xorg.conf.d/10-nvidia.conf

    Section "OutputClass"
        Identifier "nvidia"
        MatchDriver "nvidia-drm"
        Driver "nvidia"
        Option "AllowEmptyInitialConfiguration"
        Option "Coolbits" "28"
        ModulePath "/usr/lib/x86_64-linux-gnu/nvidia/xorg"
    EndSection

restart computer to take effect
