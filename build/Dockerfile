FROM jupyter/datascience-notebook
MAINTAINER youske <youske@gmail.com>
RUN cd /tmp && \
    pip install https://github.com/ipython-contrib/jupyter_contrib_nbextensions/tarball/master && \
    pip install pyyaml jupyter_nbextensions_configurator jupyter_dashboards pivottablejs ipywidgets bokeh plotly && \
    wget -q 'https://github.com/pdonorio/RISE/archive/master.tar.gz' -O - | tar zxf - && \
    cd RISE-master && python3 setup.py install && cd .. && \
    jupyter dashboards quick-setup --sys-prefix && \
    jupyter nbextensions_configurator enable --user && \
    jupyter contrib nbextension install --user
