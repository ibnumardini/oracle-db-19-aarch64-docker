# Oracle Database 19c Installation on ARM Macs (M3): Step-by-Step

## Steps to Install Oracle Database 19c on Docker

1. **Download the Oracle Database 19c Installer**
    - Visit the [Oracle Database Software Downloads](https://www.oracle.com/database/technologies/oracle-database-software-downloads.html) page.
    - Download the Oracle Database 19c for LINUX ARM (aarch64) ZIP (2.2 GB).

2. **Clone the Oracle Docker Images Repository**

    ```bash
    git clone https://github.com/oracle/docker-images.git
    ```

3. **Move the Oracle Database Installer**
    - Place the downloaded installer inside the `OracleDatabase/SingleInstance/dockerfiles/19.3.0` directory.

4. **Build the Docker Image**
    - Navigate to the dockerfiles directory and run the build script:

    ```bash
    cd OracleDatabase/SingleInstance/dockerfiles/
    ./buildContainerImage.sh -v 19.3.0 -e
    ```

5. **Verify the Docker Image**
    - After the build process completes, you should see a new image named `oracle/database` with the tag `19.3.0-ee`.

6. **Run Docker Compose**
    - Copy `.env.example` to `.env` and fill the creds.
    - Start the container using Docker Compose:

    ```bash
    docker compose up -d
    ```

7. **Donee!**
    - The setup is complete! 😊

## Additional Resources

- [Oracle on ARM Mac M1/M2 Docker Images](https://gist.github.com/miccheng/8120d2e17818ba2a2d227554b70cd34e)
- [Oracle on ARM Mac M1/M2 Docker Images - ITNEXT](https://itnext.io/oracle-on-arm-mac-m1-m2-docker-images-99ed67ed6ba6)
- [Oracle 19c with Docker - DEV Community](https://dev.to/pazyp/oracle-19c-with-docker-36m5)
