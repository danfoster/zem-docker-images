# Use the official Alpine base image
FROM alpine:latest

# Install pigz and tar
RUN apk update && apk add "pigz~2.8" "tar~1.35"

# Set the default command to display the versions of tar and pigz
CMD ["pigz"]