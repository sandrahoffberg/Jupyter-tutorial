# hash:sha256:f30a77ffe6d9357c6677f58572e5a3ed2523e589e19e2a826a9b6f9ef0af596a
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/py-r:python3.10.12-R4.2.2-IRkernel-ubuntu22.04

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN conda install -y --channel=conda-forge --channel=bioconda \
        anndata==0.9.2 \
        leidenalg==0.10.1 \
        matplotlib==3.7.2 \
        pandas==2.0.3 \
        scanpy==1.9.5 \
    && conda clean -ya

COPY postInstall /
RUN /postInstall
