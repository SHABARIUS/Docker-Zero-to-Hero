FROM ubuntu:latest

WORKDIR /app

COPY requirements.txt devops/ /app/

# Install Python, pip, and venv
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv

# Create a virtual environment
RUN python3 -m venv /app/venv

# Activate the virtual environment and install requirements
RUN /app/venv/bin/pip install -r requirements.txt

# Debug: List contents of /app/examples/first-docker-file
RUN ls -la /app/doss/examples/python-web-app

# Set environment variables to use the virtual environment
ENV PATH="/app/venv/bin:$PATH"

# Set the correct working directory if the app.py is in a nested directory
WORKDIR /app/doss/examples/python-web-app

ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]
