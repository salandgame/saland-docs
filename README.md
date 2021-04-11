# Saland homepage source

## Building
Build docker image with
```
docker build -f docker/Dockerfile . -t saland_docs_builder
```


Run the docker image with:
```
docker run -it --rm -v $(pwd)/mkdocs:/input -v $(pwd)/output:/output saland_docs_builder
```

The "output" folder should be pushed to https://github.com/salandgame/salandgame.github.io
