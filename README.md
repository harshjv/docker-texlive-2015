# Dockerised Texlive 2015


## See available tex binaries

    docker run --rm harshjv/texlive-2015 ls -lah /opt/texbin/


## Build `tex` documents


### (Optional) Update texlive packages

#### `Dockerfile`

    FROM harshjv/texlive-2015
    RUN tlmgr update --all


#### Build image

    docker build -t texlive .


### Build `tex` documents

> Use `harshjv/texlive-2015` instead of `texlive` if skipped optional step above

    docker run --rm -it -v $(pwd):/var/texlive texlive pdflatex document.tex

*or*

    docker run --rm -it -v $(pwd):/var/texlive texlive xelatex document.tex

*or see available tex commands*

    docker run --rm -it -v $(pwd):/var/texlive texlive ls -lah /opt/texbin/
