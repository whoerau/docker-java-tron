# docker-java-tron
## docker-compose
### java-tron
```
version: '3'
services:
 java-tron:
    image: java-tron
    container_name: java-tron
    restart: unless-stopped
    command:
      # - -jvm "{-Xmx10g -Xms10g}"
      - -c /java-tron/conf/main_net_config.conf
      - -d /java-tron/data
      - -w
    ports:
      - 8080:8080
      - 8090:8090
      - 18888:18888
      - 50051:50051
    volumes:
      - ./conf:/java-tron/conf
      - ./data:/java-tron/data
      - ./logs:/java-tron/logs
```

### java-tron-with-plugin
```
version: '3'
services:
 java-tron-with-plugin:
    image: java-tron-with-plugin
    container_name: java-tron-with-plugin
    restart: unless-stopped
    command:
      # - -jvm "{-Xmx10g -Xms10g}"
      - -c /java-tron/conf/main_net_config.conf
      - -d /java-tron/data
      - -w
      - --es
    ports:
      - 8080:8080
      - 8090:8090
      - 18888:18888
      - 50051:50051
    volumes:
      - ./conf:/java-tron/conf
      - ./data:/java-tron/data
      - ./logs:/java-tron/logs
```
