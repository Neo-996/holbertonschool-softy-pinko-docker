# Use latest Ubuntu base image
FROM ubuntu:latest

# Update and upgrade packages
RUN apt-get update && apt-get upgrade -y

# Install Python3 and pip
RUN apt-get install -y python3 python3-pip

# Fix EXTERNALLY-MANAGED error if needed
RUN rm -f /usr/lib/python*/EXTERNALLY-MANAGED || true

# Install Flask using pip3
RUN pip3 install flask

# Set working directory
WORKDIR /app

# Copy Flask app into the image
COPY ./api.py /app/api.py

# Expose port Flask will run on
EXPOSE 5252

# Run Flask app
CMD ["python3", "api.py"]
