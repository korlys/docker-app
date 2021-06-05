docker run -it --rm busybox


Create a Dockerfile for a binary

```
FROM busybox
COPY ./my-static-binary /my-static-binary
CMD ["/my-static-binary"]
```