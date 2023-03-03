<h1>markbajaj/iperf3</h1>

A tiny Docker image of iperf3 based on Alpine Linux. Prebuilt images for linux/amd64, linux/arm64 and linux/arm/v7 are provided.

<b>Usage</b>

Run an iperf3 server as a container called 'iperf3' detached with the following command:
```
docker run --name=iperf3 -d --restart=unless-stopped -p 5201:5201/tcp -p 5201:5201/udp markbajaj/iperf3:latest
```
<br>
<b>Docker-compose.yml</b><br>

```
version: "2.1"
services:
  iperf3:
    image: markbajaj/iperf3:latest
    container_name: iperf3
    ports:
      - 5201:5201/udp
      - 5201:5201/tcp
    restart: unless-stopped
```

<b>Build</b>

Clone the repository:<br>
```
git clone https://github.com/markbajaj/iperf3.git
```
```
cd iperf3
```
<br>
<b>Build the image: </b><br><br>

```
docker build -t markbajaj/iperf3:latest . 
```
<br>
<b>Build for other architectures:</b><br><br>
You can also use docker buildx to build the image for multiple architectures.

Update to Docker 19.03 or later, and enable experimental features.

Run the build using buildx command:<br>
```
docker buildx build --platform linux/amd64,linux/arm64,linux/arm/v7 --push -t markbajaj/iperf3:latest .
```
Builds on riscv and arm/v6 are not included in the command.
