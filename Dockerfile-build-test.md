# Test

The goal of Dockerfile is to serve as a test to show that our setup would work on machine without any dependencies installed.

Ensure that commands to run `Pistache` work on a fresh machine.

## Docs

```txt
# Build the image:
docker build -f Dockerfile.build-test -t build-test .

# Run the container:
docker run -p 9080:9080 build-test
```
