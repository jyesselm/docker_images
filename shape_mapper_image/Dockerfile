################## BASE IMAGE ######################

FROM biocontainers/biocontainers:latest

################## METADATA ######################
LABEL base.image="biocontainers:latest"
LABEL version="1"
LABEL software="shapemapper"
LABEL software.version="2.0"
LABEL about.summary="weeks lab analysis of shape data"
LABEL about.tags="RNA bioinformatics,RNA structure"

################## MAINTAINER ######################
MAINTAINER Joe Yesselman <jyesselm@unl.edu>

################## INSTALLATION ######################
ENV DST=/home/biodocker/bin

USER root
## setup correct python and packages
RUN conda create --name py3 python=3.8 --yes
ENV PATH /opt/conda/envs/py3/bin:$PATH
RUN /bin/bash -c "source activate py3"
RUN echo "source activate py3" > ~/.bashrc
# not sure if I need this anymore
RUN pip install cython

# download shapemapper
RUN wget https://github.com/Weeks-UNC/ShapeMapper2/releases/download/2.1.5/shapemapper-2.1.5.tar.gz && \
    tar -xvf shapemapper-2.1.5.tar.gz

WORKDIR /data/shapemapper-2.1.5

# Change user
# USER biodocker


CMD ["/bin/bash"]
