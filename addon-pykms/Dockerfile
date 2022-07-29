FROM alpine:latest as prep

RUN apk add --no-cache git && \
	git clone https://github.com/automatorz/py-kms /app


FROM python:3.9 as pykms

COPY --from=prep /app/py-kms /app
WORKDIR /app

COPY requirements.txt ./
RUN pip install --upgrade pip && \
	pip install --no-cache-dir -r requirements.txt

CMD ["/app/pykms_Server.py"]
