FROM jupyter/datascience-notebook:latest
MAINTAINER Daniel Sakuma "dsakuma@gmail.com"

USER jovyan

COPY requirements.txt ./
RUN pip install --upgrade pip \
    && pip install -r requirements.txt
