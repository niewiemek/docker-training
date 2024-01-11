# docker-training
Some docker excessed used on Docker Basics training

## Dockerfile command summary
```
FROM image:tag      # FROM image:tag AS buildStageAlias
ENV                 # sets and define default environment variables
RUN ...             # any shell command
COPY host container # host path is relative to a Dockerfile
COPY --from=buildStageAlias host container # copy from a build stage image
WORKDIR ...         # changes current workdir in 
USER ...            # change current user (default root - not recommended)
CMD / ENTRYPOINT ...# provide defaults for an executing container
```
