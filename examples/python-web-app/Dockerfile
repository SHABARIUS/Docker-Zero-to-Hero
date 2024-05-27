FROM ubuntu

WORKDIR /app

COPY requirements.txt /app
COPY devops /app

# Install Python, pip, and venv
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv

# Create a virtual environment
RUN python3 -m venv /app/venv

# Activate the virtual environment and install requirements
RUN /app/venv/bin/pip install -r requirements.txt

# Set environment variables to use the virtual environment
ENV PATH="/app/venv/bin:$PATH"

ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]




