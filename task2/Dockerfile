# Step 1: Use the latest version of Ubuntu as the base image
FROM ubuntu:latest

# Step 2: Update APT packages and upgrade installed software
RUN apt-get update && apt-get upgrade -y

# Step 3: Install Python3 and pip3
RUN apt-get install -y python3 python3-pip

# Step 4: Remove EXTERNALLY-MANAGED file to avoid pip errors
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED

# Step 5: Install Flask using pip3
RUN pip3 install flask

# Step 6: Set the working directory to /app
WORKDIR /app

# Step 7: Copy the Python file into the Docker image
COPY ./api.py /app/api.py

# Step 8: Run the Flask application
CMD ["python3", "api.py"]
