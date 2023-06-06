#Builder creates file and saves data

FROM alpine AS builder
WORKDIR /app
#RUN touch newfile.txt && echo something, something
RUN echo 123123123 > testfile.txt

# creates new docker file with python

FROM python:3.12.0b1-slim-buster
WORKDIR /app

# copy from different stage/step
COPY --from=builder /app/testfile.txt .

#copy python script
COPY script.py .

#execute, last command
ENTRYPOINT ["python", "script.py"]

#cmd -  allows to overwrite final step
CMD ["/bin/sh"]