FROM python:3.7
# Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1
# Set work directory
WORKDIR /code/django_data/
# Install dependencies
COPY requirements.txt .
RUN pip install -r requirements.txt
# Copy project
COPY . .
# Make migrations