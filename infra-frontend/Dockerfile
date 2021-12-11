FROM openjdk:8u181-alpine3.8

# Make a directory
RUN mkdir -p /infra-frontend
WORKDIR /infra-frontend

# Install python3, curl
RUN apk update \
    && apk upgrade \
    && apk add curl \
    && apk add screen \
    && apk add --no-cache python3 py3-pip

# Copy only the quotes jar over
COPY . .

# Open the port
EXPOSE 8080

# Run the JAR
CMD ["sh", "-c", "cd front-end/public ; screen -dmS server python3 ./serve.py ; cd ../.. ; java -jar build/front-end.jar"]
