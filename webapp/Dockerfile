FROM python:3.9-slim
WORKDIR /app
# This copies requirements.txt from your "webapp folder" into the container
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
# This copies app.py into the container
COPY app.py .
CMD ["python", "app.py"