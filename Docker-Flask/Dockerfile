# 1. Base image — official slim variant for smaller size
FROM python:3.11-slim

# 2. Working directory inside the container
WORKDIR /app

# 3. Copy dependencies FIRST to leverage layer caching
COPY requirements.txt .

# 4. Install dependencies; --no-cache-dir keeps the image small
RUN pip install --no-cache-dir -r requirements.txt

# 5. Copy the rest of the application code
COPY . .

# 6. Document the listening port
EXPOSE 5000

# 7. Default command when the container starts
CMD ["python", "app.py"]