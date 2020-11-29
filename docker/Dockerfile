# Usage:
# Build: docker build -f docker/Dockerfile . -t saland_docs_builder
# Run: docker run -it --rm -v $(pwd)/mkdocs:/input -v $(pwd)/output:/output saland_docs_builder

FROM ubuntu:20.04

RUN apt-get update && apt-get install --no-install-recommends -y python3 python3-pip rsync
RUN pip3 install --upgrade mkdocs==1.1.2 mkdocs-material==5.5.12

RUN mkdir -p /workdir && mkdir -p /output

VOLUME /output
VOLUME /input

RUN adduser --disabled-password --gecos "Build user" builduser && chown builduser /workdir
USER builduser

CMD rsync -r /input/ /workdir && cd /workdir && mkdocs build && rsync -r /workdir/site/ /output
