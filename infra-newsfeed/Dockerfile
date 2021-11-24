FROM openjdk:8u181-alpine3.8

# Make a directory
RUN mkdir -p /newsfeed
WORKDIR /newsfeed

# Copy only the quotes jar over
COPY build/newsfeed.jar .

# Open the port
EXPOSE 8080

# Run the JAR
CMD java -jar newsfeed.jar