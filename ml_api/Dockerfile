FROM yaphets1/ml_api_base:latest
WORKDIR /app
EXPOSE 3333

ADD . /app
RUN pip3 install --upgrade pip
RUN pip3 install -r requirements.txt
RUN pip3 install --upgrade "sentry-sdk[flask]"

RUN echo 'Downloading the latest failure detection AI model in Darknet format...'
RUN wget -O model/model-weights.darknet $(cat model/model-weights.darknet.url | tr -d '\r')
RUN echo 'Downloading the latest failure detection AI model in ONNX format...'
RUN wget -O model/model-weights.onnx $(cat model/model-weights.onnx.url | tr -d '\r')