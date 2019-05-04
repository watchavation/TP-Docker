FROM python:2.7
LABEL hub_url watchavation/docker_tp_frontend
RUN pip install requests Flask
WORKDIR /app
COPY ./api.py /app
EXPOSE 8000
ENTRYPOINT [ "python" ]
CMD [ "/app/api.py" ]  
