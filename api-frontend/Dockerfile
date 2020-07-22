FROM python:3
LABEL hub_url watchavation/docker_tp_frontend
#RUN pip install requests Flask
RUN apt update -y && apt install -y python-requests python-flask
WORKDIR /app
COPY ./api.py /app
EXPOSE 8000
ENTRYPOINT [ "python" ]
CMD [ "/app/api.py" ]  
