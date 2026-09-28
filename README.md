Cosplaying as a SysAdmin


Data Directory
Folder Mapping

It's good practice to give all containers the same access to the same root directory or share. This is why all containers in the compose file have the bind volume mount /data:/data. It makes everything easier, plus passing in two volumes such as the commonly suggested /tv, /movies, and /downloads makes them look like two different file systems, even if they are a single file system outside the container. See my current setup below.

data
├── movies
├── music
└── shows
docker
└── jellyfin
    ├── config
    └── jellystat


Data Directory
Folder Mapping

It's good practice to give all containers the same access to the same root directory or share. This is why all containers in the compose file have the bind volume mount /data:/data. It makes everything easier, plus passing in two volumes such as the commonly suggested /tv, /movies, and /downloads makes them look like two different file systems, even if they are a single file system outside the container. See my current setup below.

data
├── books
├── downloads
│   ├── qbittorrent
│   │   ├── completed
│   │   ├── incomplete
│   │   └── torrents
│   └── nzbget
│       ├── completed
│       ├── intermediate
│       ├── nzb
│       ├── queue
│       └── tmp
├── movies
├── music
├── shows
└── youtube

Here is an easy command to create the download directory scheme. Run within the /data directory.

mkdir -p downloads/qbittorrent/{completed,incomplete,torrents}
