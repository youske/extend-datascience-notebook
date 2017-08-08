FROM jupyter/datascience-notebook
MAINTAINER youske <youske@gmail.com>
RUN cd /tmp && \
    pip install numpy param pyyaml py_d3 paramiko && \
    pip install https://github.com/ipython-contrib/jupyter_contrib_nbextensions/tarball/master && \
    pip install jupyter_nbextensions_configurator jupyter_dashboards jupyterthemes ipywidgets bash_kernel pivottablejs && \
    conda install -c ioam holoviews bokeh plotly && \
    wget -q 'https://github.com/pdonorio/RISE/archive/master.tar.gz' -O - | tar zxf - && \
    cd RISE-master && python3 setup.py install && cd .. && \
    jupyter dashboards quick-setup --sys-prefix && \
    jupyter nbextensions_configurator enable --user && \
    jupyter contrib nbextension install --user && \
    python -m bash_kernel.install --user
