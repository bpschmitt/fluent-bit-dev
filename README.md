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

# Expected result

```
Fluent Bit v1.9.0
* Copyright (C) 2015-2021 The Fluent Bit Authors
* Fluent Bit is a CNCF sub-project under the umbrella of Fluentd
* https://fluentbit.io

[2022/03/22 20:19:43] [ info] [engine] started (pid=1)
[2022/03/22 20:19:43] [ info] [storage] version=1.1.6, initializing...
[2022/03/22 20:19:43] [ info] [storage] in-memory
[2022/03/22 20:19:43] [ info] [storage] normal synchronization mode, checksum disabled, max_chunks_up=128
[2022/03/22 20:19:43] [ info] [cmetrics] version=0.3.0
[2022/03/22 20:19:43] [ info] [input:forward:forward.0] listening on 0.0.0.0:24224
[2022/03/22 20:19:43] [ info] [sp] stream processor started
[2022/03/22 20:19:43] [ info] [output:stdout:stdout.0] worker #0 started
[0] 7a1747d7dd06: [1647980398.000000000, {"container_id"=>"7a1747d7dd0656eaec932b5bde029a904b4463d188b210b60fe3021f9f8b1e90", "container_name"=>"/eloquent_jemison", ", "test_field"=>"hooray"}]"Testing a log message
```

