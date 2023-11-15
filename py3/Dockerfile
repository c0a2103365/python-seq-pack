FROM python:3.9.7-buster
ARG DEBIAN_FRONTEND=noninteractive

# パッケージの追加とタイムゾーンの設定
# 必要に応じてインストールするパッケージを追加してください
RUN apt-get update && apt-get install -y \
    tzdata \
&&  ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime \
&&  apt-get clean \
&&  rm -rf /var/lib/apt/lists/*

ENV TZ=Asia/Tokyo

RUN apt-get update \
    &&apt-get install -y sudo \
    && sudo apt-get install -y mecab \
    && sudo apt-get install -y libmecab-dev \
    && sudo apt-get install -y mecab-ipadic-utf8 \
    && sudo apt-get install -y make \
    && sudo apt install -y --reinstall build-essential \
    && sudo apt-get install -y swig \
    && sudo apt install -y graphviz \
    && sudo apt-get install -y graphviz-dev \
    && sudo apt-get install -y python3-graphviz

# JupyterLab関連のパッケージ（いくつかの拡張機能を含む）
RUN python3 -m pip install --upgrade pip \
&&  pip install --no-cache-dir \
    black \
    jupyterlab \
    jupyterlab_code_formatter \
    jupyterlab-git \
    lckr-jupyterlab-variableinspector \
    jupyterlab_widgets \
    ipywidgets \
    import-ipynb

RUN pip install --no-cache-dir \
    numpy \
    pandas \
    scipy \
    scikit-learn \
    pycaret \
    matplotlib \
    japanize_matplotlib \
    mlxtend \
    seaborn \
    plotly \
    requests \
    beautifulsoup4 \
    selenium \
    tensorflow[and-cuda] \
    tensorrt \
    torch \
    keras \
    networkx \
    pygraphviz  \
    graphviz \
    lightly \
    LightGBM \
    xgboost \
    catboost