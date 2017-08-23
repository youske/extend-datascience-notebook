FROM jupyter/datascience-notebook
MAINTAINER youske <youske@gmail.com>

USER root
RUN apt-get update && apt-get install -y openssh git libtool make libffi-dev libzmq3-dev autoconf pkg-config && \
    cd /tmp && git clone https://github.com/zeromq/czmq && \
    cd czmq && ./autogen.sh && ./configure && make && make install

USER $NB_USER
RUN cd /tmp && \
    conda install -c ruby numpy scipy cython numba paramiko requests && \
    conda install -c ioam holoviews bokeh plotly seaborn && \
    pip install param pyyaml py_d3 ansible testinfra pyinvoke && \
    pip install https://github.com/ipython-contrib/jupyter_contrib_nbextensions/tarball/master && \
    pip install jupyter_nbextensions_configurator jupyter_dashboards jupyterthemes ipywidgets bash_kernel remote_ikernel pivottablejs && \
    wget -q 'https://github.com/pdonorio/RISE/archive/master.tar.gz' -O - | tar zxf - && \
    cd RISE-master && python3 setup.py install && cd .. && \
    npm install -g ijavascript && \
    jupyter dashboards quick-setup --sys-prefix && \
    jupyter nbextensions_configurator enable --user && \
    jupyter contrib nbextension install --user && \
    python -m bash_kernel.install --user && \
    gem install cztop iruby nyaplot rubyvis pry awesome_print && \
    iruby register --force

