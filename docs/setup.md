# Setup


## Prerequisites
- **[Windows Subsystem for Linux (WSL 2)](https://learn.microsoft.com/en-us/windows/wsl/install) for Windows**: Not required, but ***highly*** recommended. Allows development to be done on linux instead of Windows.
- **AWS**: An Amazon Web Services (AWS) account is required, though if everything is done correctly, only the [free tier](https://aws.amazon.com/free/) is required.
- **Go**: Version 1.26+ installed on the local development machine.
- **[SQLite 3](https://www.sqlite.org/download.html)**: Installed on the local development machine to be able to use the CLI to manually inspect the database.


## One-time Setup Steps
- Fork the [starter repo for this course](https://github.com/bootdotdev/learn-file-storage-s3-golang-starter/) into a personal GitHub namespace, then clone that fork onto the local development machine.
- Create the `.env` file:  
    ```bash
    cp .env.example .env
    ```
- Run the script called `samplesdownload.sh` from the root of the repo to download some sample images and videos into the `samples` directory:
    ```bash
    ./samplesdownload.sh
    ```
- With the server running, create a Tubely account by entering the following email and password and clicking "sign up":  
    Email: `admin@tubely.com`  
    Password: `password`
- Install SQLite 3.
    ```bash
    sudo apt update
    sudo apt install sqlite3
    ```


## Running the server
```bash
go run .
```
A URL will be logged to the console. The URL can be opened in a browser to see the Tubely app.


## Troubleshooting, copied directly from the lesson:
If you get an error that says "go-sqlite3 requires cgo to work", you need to:

1. Install gcc:  
    **on macOS:**
    ```bash
    brew install gcc
    ```
    **or Linux:**
    ```bash
    sudo apt install gcc
    ```
2. Ensure the environment variable `CGO_ENABLED` is set to 1:
    ```bash
    go env CGO_ENABLED

    # If the command above prints 0, run this:
    go env -w CGO_ENABLED=1
    ```
