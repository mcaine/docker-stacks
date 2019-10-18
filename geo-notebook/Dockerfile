# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.
ARG BASE_CONTAINER=jupyter/scipy-notebook
FROM $BASE_CONTAINER

LABEL maintainer="Jupyter Project <jupyter@googlegroups.com>"

# Install geo stuff
#RUN conda install --quiet --yes \
#    'tensorflow=1.13*' \
#    'keras=2.2*' && \
#    'Fiona' \
#    'Jinja2' \
#    'MarkupSafe' \
#    'Pillow' \
#    'PySAL' \
#    'shapely' \
#    'lxml' \
#    'matplotlib' \
#    'descartes' && \
#    conda clean --all -f -y && \
#    fix-permissions $CONDA_DIR && \
#    fix-permissions /home/$NB_USER

RUN conda install --yes cartopy && \
    fix-permissions $CONDA_DIR && \
    fix-permissions /home/$NB_USER

RUN conda install --yes -c conda-forge pythreejs

RUN pip install k3d
RUN jupyter nbextension enable --py --sys-prefix k3d
RUN conda install -c conda-forge contextily
RUN conda install --channel conda-forge geopandas
RUN conda install --channel conda-forge descartes

RUN fix-permissions $CONDA_DIR && \
    fix-permissions /home/$NB_USER


