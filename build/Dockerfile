FROM jupyter/datascience-notebook
MAINTAINER youske <youske@gmail.com>
RUN pip install pyyaml && \
    pip install jupyter_dashboards && \
    jupyter dashboards quick-setup --sys-prefix && \
    wget -q https://github.com/pdonorio/RISE/archive/master.tar.gz && \
    tar xvzf *.gz && cd RISE-master && python3 setup.py install && \
    cd .. && \
    pip install jupyter_nbextensions_configurator && \
    jupyter nbextensions_configurator enable --user && \
    pip install https://github.com/ipython-contrib/jupyter_contrib_nbextensions/tarball/master && \
    jupyter contrib nbextension install --user 
