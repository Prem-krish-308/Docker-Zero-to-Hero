FROM ubuntu

WORKDIR /app

COPY requirements.txt /app/
COPY devops /app/

# Install dependencies
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv && \
    rm -rf /var/lib/apt/lists/*

# Create virtual environment
RUN python3 -m venv /app/venv

# Install Python dependencies
RUN /app/venv/bin/pip install --no-cache-dir -r requirements.txt

# Expose port
EXPOSE 8000

# Run app using venv python
CMD ["/app/venv/bin/python", "manage.py", "runserver", "0.0.0.0:8000"]
