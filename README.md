# Dockerfile Working Directory Bug

This example demonstrates a common error in Dockerfiles: not specifying a working directory.  This can lead to issues when copying files and executing commands within the container.

The `Dockerfile` uses a `COPY` instruction to copy files. Because no `WORKDIR` is defined the application files will be placed in `/`. Executing the application then fails as the script tries to access data files that are not in the same directory.

The `DockerfileSolution` provides a corrected version, adding a `WORKDIR` instruction to define where files should be copied and where commands should run.