FROM openjdk:8u181-alpine3.8

# Make a directory
RUN mkdir -p /infra-frontend
WORKDIR /infra-frontend

# Install python3, curl
RUN apk update \
    && apk upgrade \
    && apk add curl \
    && apk add --no-cache python3 py3-pip

# Copy only the quotes jar over
COPY . .

# Open the port
EXPOSE 8080

# Execute the static content
#ENTRYPOINT ["/bin/ash", "-c" , "cd /infra-frontend/front-end/public && nohup python3 ./serve.py > log.txt 2>&1 &"]

# Run the JAR
CMD java -jar build/front-end.jar