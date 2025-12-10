FROM ubuntu

WORKDIR /app

COPY requirements.txt /app/
COPY devops /app/

RUN apt-get update && apt-get install -y python3 python3-pip python3-venv

# Create virtual environment
RUN python3 -m venv venv1

# Install requirements using the virtual env's pip
RUN /app/venv1/bin/pip install --no-cache-dir -r requirements.txt

EXPOSE 8000

# Directly call python from the venv instead of using 'source'
CMD ["/app/venv1/bin/python3", "manage.py", "runserver", "0.0.0.0:8000"]
