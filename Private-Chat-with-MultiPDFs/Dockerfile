FROM python:3.9


ENV HOST=0.0.0.0
ENV LISTEN_PORT 8501
EXPOSE 8501

# Create app directory
WORKDIR /app

# Copy the files
COPY requirements.txt ./requirements.txt


#install the dependecies
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

HEALTHCHECK CMD curl --fail http://localhost:8501/_stcore/health


COPY ./cmd /app/cmd


CMD ["streamlit", "run", "cmd/app.py", "--server.port", "8501"]