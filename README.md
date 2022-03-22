# fluent-bit-dev

Just a repo to hold some of my Fluent Bit testing artifacts

# Set up your Docker container
```
export FB_CONF=/path/to/your/fluent-bit.conf

docker run -p 127.0.0.1:24224:24224 -v $FB_CONF:/fluent-bit/etc/fluent-bit.conf fluent/fluent-bit:latest /fluent-bit/bin/fluent-bit -c /fluent-bit/etc/fluent-bit.conf
```

# Quick test
```
docker run --log-driver=fluentd -t ubuntu echo "Testing a log message"
```

