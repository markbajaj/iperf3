<h1>markbajaj/iperf3</h1>

A tiny Docker image of iperf3 based on Alpine Linux. Prebuilt images for linux/amd64, linux/arm64 and linux/arm/v7 are provided.

<b>Usage</b>

Run an iperf3 server as a container called 'iperf3' detached with the following command:

docker run --name=iperf3 -d --restart=unless-stopped -p 5201:5201/tcp -p 5201:5201/udp markbajaj/iperf3:latest

<b>Build</b>

Clone the repository:<br><br>
git clone https://github.com/markbajaj/iperf3.git <br><br>
cd iperf3 <br>
<b>Build the image: </b><br><br>
docker build -t markbajaj/iperf3:latest . <br><br>
<b>Build for other architectures:</b><br>
You can also use docker buildx to build the image for multiple architectures.

Update to Docker 19.03 or later, and enable experimental features.

Run the build command:

docker buildx build --platform linux/amd64,linux/arm64,linux/arm/v7 --push -t markbajaj/iperf3:latest .

Builds on riscv and arm/v6 are not included in the command.
