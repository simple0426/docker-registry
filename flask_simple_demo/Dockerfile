FROM python:2.7
LABEL maintainer='istyle.simple@gmail.com'
COPY app.py /app
RUN pip install redis flask
WORKDIR /app
EXPOSE 5000
CMD ["python", "app.py"]
