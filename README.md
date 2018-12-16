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