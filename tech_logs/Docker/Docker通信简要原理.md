要使 Docker 容器内的应用与本地外部应用进行通信，你可以使用以下几种方法：

1. 端口映射（Port Mapping）：使用端口映射，将容器内的应用端口映射到本地主机的端口上。这使得本地外部应用可以通过访问本地主机的特定端口来与容器内的应用进行通信。你可以使用 Docker 命令行选项 `-p` 或 `--publish` 来指定端口映射规则。

   ```bash
   docker run -p <host_port>:<container_port> <image_name>
   ```

   例如，要将容器内的应用的端口 8080 映射到本地主机的端口 8000，可以使用以下命令：

   ```bash
   docker run -p 8000:8080 <image_name>
   ```

   然后，本地外部应用可以通过访问 `localhost:8000` 来与容器内的应用进行通信。

2. 主机网络模式（Host Network Mode）：使用主机网络模式，容器将与主机的网络共享同一个网络命名空间。这意味着容器内的应用将直接使用主机的网络接口，与本地外部应用进行通信时，就像与主机上的应用进行通信一样。要使用主机网络模式，可以在 Docker 命令中使用 `--network host` 选项。

   ```bash
   docker run --network host <image_name>
   ```

   使用主机网络模式时，容器内的应用可以通过使用本地主机的 IP 地址和端口来与本地外部应用进行通信。

3. 共享数据卷（Shared Volumes）：使用共享数据卷，可以将容器内的文件系统路径与本地主机的文件系统路径进行映射。这使得容器内的应用可以读写本地文件系统上的文件，并通过共享文件来与本地外部应用进行通信。要使用共享数据卷，可以在 Docker 命令中使用 `-v` 或 `--volume` 选项。

   ```bash
   docker run -v <host_path>:<container_path> <image_name>
   ```

   例如，要将本地主机的 `/path/to/local` 目录映射到容器内的 `/path/to/container` 目录，可以使用以下命令：

   ```bash
   docker run -v /path/to/local:/path/to/container <image_name>
   ```

   然后，容器内的应用可以读写 `/path/to/container` 目录中的文件，与本地外部应用进行通信。

以上是一些常见的方法，使得容器内的应用可以与本地外部应用进行通信。你可以根据你的具体需求选择适合的方法。