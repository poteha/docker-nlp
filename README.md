## How to use

In your docker file write `FROM iwitaly/nlp:cpu` for CPU version or `FROM iwitaly/nlp:gpu` for GPU version.

Find the image at Docker hub https://hub.docker.com/r/iwitaly/nlp/


## Whats inside

Modern NLP frameworks including deep learning:
* torch==0.4.1
* flair==0.3.2
* spacy==2.0.11
* dateparser==0.7.0
* pymorphy2==0.8
* yargy==0.11.0
* natasha==0.10.0
* nltk==3.2.1
* yake==0.3.7


## How to build


### CPU

```bash
docker build -t nlp-cpu -f ./Dockerfile.cpu .
```

### GPU

```bash
docker build -t nlp-gpu -f ./Dockerfile.gpu .
```

Please keep in mind that this version works with CUDA 10. Choose another base image if your GPU does not support it.

You can find NVIDIA images here https://hub.docker.com/r/nvidia/cuda/

## How to use

`docker run -it --runtime=nvidia iwitaly/nlp:gpu nvidia-smi`

You can also pass `CUDA_VISIBLE_DEVICES` environment variable.