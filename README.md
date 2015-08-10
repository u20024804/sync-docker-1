BitTorrent Sync
===============

Sync uses peer-to-peer technology to provide fast, private file sharing for teams and individuals. By skipping the cloud, transfers can be significantly faster because files take the shortest path between devices. Sync does not store your information on servers in the cloud, avoiding cloud privacy concerns.

# Usage

    DATA_FOLDER=/path/to/data/folder/on/the/host
    WEBUI_PORT=[ port to access the webui on the host ]

    mkdir -p $DATA_FOLDER

    docker run -d --name Sync \
      -p 127.0.0.1:$WEBUI_PORT:8888 -p 55555 \
      -v $DATA_FOLDER:/mnt/sync \
      --restart on-failure \
      bittorrent/sync

Go to localhost:$WEBUI_PORT in a web browser to access the webui.

# Volume

* /mnt/sync - State files and Sync folders

# Ports

* 8888 - Webui
* 55555 - Listening port for Sync traffic
