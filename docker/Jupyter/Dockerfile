FROM jupyter/minimal-notebook

COPY ./docker/Jupyter/requirements.txt /tmp/requirements.txt
RUN pip install -r /tmp/requirements.txt
RUN pip install matplotlib