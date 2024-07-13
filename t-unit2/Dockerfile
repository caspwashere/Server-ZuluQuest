FROM python:3.8

## Copy local code to the container image.
ENV APP_HOME /app
WORKDIR $APP_HOME
COPY . ./
COPY t-unit2/requirements.txt .

# Install packages.
RUN pip install -r requirements.txt

# Set an environment variable for the port 5000.
ENV PORT 5000

# Run gunicorn bound to the 5000 port.
CMD exec gunicorn --bind 0.0.0.0:$PORT --workers 1 --threads 8 server:app
