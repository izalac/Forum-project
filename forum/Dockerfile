FROM python:3.12.10-alpine3.21

# System update
RUN apk update
RUN apk upgrade
RUN apk add build-base
RUN python3 -m pip install --upgrade pip

# Install requirements
WORKDIR /app
COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

#adds the rest of the files
COPY . .

# Networking
EXPOSE 5000

# Runs the container
CMD ["python3", "-m" , "flask", "run", "--host=0.0.0.0"]
