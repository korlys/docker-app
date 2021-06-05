damselfly
  damselfly: 
        container_name: damselfly
        image: webreaper/damselfly
        ports:
            - 6363:6363/tcp
        volumes:
            - /volume1/dockerdata/damselfly:/config
            - /volume1/dockerdata/damselfly/thumbs:/thumbs
            - /volume1/photo:/pictures 
        restart: unless-stopped