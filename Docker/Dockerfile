# Build stage
FROM python:3.8 AS build-stage
WORKDIR /app
COPY ./requirements.txt .
COPY ./app /app
RUN pip install -r requirements.txt

# Final stage
FROM python:3.8
WORKDIR /app
COPY --from=build-stage /app /app
CMD [ "python", "app.py" ]