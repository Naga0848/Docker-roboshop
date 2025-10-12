FROM python:3.9
EXPOSE 8080
WORKDIR /opt/server
COPY *.py .
COPY requirments.txt .
COPY payment.ini .
RUN pip3 install -r requirments.txt
CMD ["usgi", "--ini", "payments.ini"]

