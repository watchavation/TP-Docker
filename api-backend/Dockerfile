FROM python:2.7
LABEL hub_url watchavation/docker_tp_backend
WORKDIR /app
RUN pip install requests Flask
COPY ./api.py /app
CMD ["python", "api.py"]
EXPOSE 8001
