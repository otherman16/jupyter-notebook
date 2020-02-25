ARG BASE_CONTAINER=otherman16/jupyter-notebook-scipy
FROM $BASE_CONTAINER

LABEL maintainer="Aleksey Kobylin <alexeykob16@gmail.com>"

# Install torch with cuda 10.1 and torch-ecosystem
RUN conda install --quiet --yes pytorch torchvision cudatoolkit=10.1 -c pytorch \
    && \
    python3 -m pip install \
    	catalyst \
	albumentations \
	pretrainedmodels \
	segmentation-models-pytorch \
	alchemy-catalyst \
	tensorflow==2.1.0 \
	opencv-python \
    && \
    conda clean --all -f -y \
    && \
    fix-permissions $CONDA_DIR && \
    fix-permissions /home/$NB_USER

EXPOSE 6006
