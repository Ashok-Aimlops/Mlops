FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Copy the wheel and requirements
COPY bikeshare_model-0.0.1-py3-none-any.whl .
COPY requirements.txt .

RUN pip install --upgrade pip 
# Install wheel and dependencies
RUN pip install --no-cache-dir bikeshare_model-0.0.1-py3-none-any.whl
RUN pip install --no-cache-dir -r requirements.txt

# Copy FastAPI app code
COPY app/ ./app/

# Expose FastAPI port
EXPOSE 8001

# Run the app
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8001"]
