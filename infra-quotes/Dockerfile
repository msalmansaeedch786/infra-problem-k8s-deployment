FROM openjdk:8u181-alpine3.8

# Make a directory
RUN mkdir -p /quotes
WORKDIR /quotes

# Copy only the quotes jar over
COPY build/quotes.jar .

# Open the port
EXPOSE 8080

# Run the JAR
CMD java -jar quotes.jar