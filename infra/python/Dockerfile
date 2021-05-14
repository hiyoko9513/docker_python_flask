FROM python:3.9
USER root
SHELL ["/bin/bash", "-c"]

# FROM 内での利用宣言（宣言しておかないと受け取れない）
# ARG workdir
# 変数を環境変数にセット
# ENV workdir=$workdir

RUN apt-get update && \
  pip install --upgrade pip && \
  pip install --upgrade setuptools

# serverのロケールの変更
RUN apt-get -y install locales && \
  localedef -f UTF-8 -i ja_JP ja_JP.UTF-8
ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV LC_ALL ja_JP.UTF-8
ENV TZ JST-9
ENV TERM xterm
ENV PYTHONUNBUFFERED 1

RUN mkdir -p /hiyoko
WORKDIR /hiyoko
ADD ./requirements.txt /hiyoko/
RUN pip install -r requirements.txt

EXPOSE 5000

# vimをインストール
# RUN apt-get install -y vim less

# djangoのインストール
# RUN pip install django && \
#   pip install djangorestframework && \
#   pip install django-cors-headers && \
#   pip install djangorestframework_simplejwt && \
#   django-admin startproject $workdir && \
#   python $workdir/manage.py migrate && \
#   django-admin startapp $workdir
