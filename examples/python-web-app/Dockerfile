# Use an official Ubuntu base image
FROM ubuntu:latest

# Set the working directory to /app
WORKDIR /app

# Copy the requirements file and devops directory into the container at /app
COPY requirements.txt /app/
COPY devops /app/devops/

# Update the package list, install Python3, pip, and venv for creating virtual environments
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv

# Create a virtual environment in the /app/venv directory and install the requirements
RUN python3 -m venv /app/venv && \
    /app/venv/bin/pip install -r /app/requirements.txt

# Set the PATH environment variable to use the virtual environment
ENV PATH="/app/venv/bin:$PATH"

# Set the entry point and default command for the container
ENTRYPOINT ["python3", "devops/manage.py"]
CMD ["runserver", "0.0.0.0:8000"]




