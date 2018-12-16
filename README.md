## How to use

In your docker file write `FROM iwitaly/nlp:cpu` for CPU version or `FROM iwitaly/nlp:gpu` for GPU version.

Find the image at Docker hub https://hub.docker.com/r/iwitaly/nlp/


## How to build


### CPU

```bash
docker build -t nlp-cpu -f ./Dockerfile.cpu .
```

### GPU

```bash
docker build -t nlp-gpu -f ./Dockerfile.gpu .
```

## How to use

`docker run -it --runtime=nvidia iwitaly/nlp:gpu nvidia-smi`

You can also pass `CUDA_VISIBLE_DEVICES` environment variable.