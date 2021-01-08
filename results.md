# PERF RESULTS

command:
```
echo 'GET http://localhost:3000/rest/products/search?q=' | vegeta attack -rate=3/s -duration=5m -name=with-agent-protect -output=with-agent-protect.bin
```

## without-agent

```
Average container CPU% is 17.01 and MEM% is 2.22

Requests      [total, rate, throughput]         900, 3.00, 3.00
Duration      [total, attack, wait]             5m0s, 5m0s, 33.392ms
Latencies     [min, mean, 50, 90, 95, 99, max]  23.91ms, 34.103ms, 32.853ms, 39.268ms, 42.613ms, 76.33ms, 126.205ms
Bytes In      [total, mean]                     11785500, 13095.00
Bytes Out     [total, mean]                     0, 0.00
Success       [ratio]                           100.00%
Status Codes  [code:count]                      200:900
Error Set:

```

## with-agent-assess

```
Average container CPU% is 105.60 and MEM% is 13.48

Requests      [total, rate, throughput]         900, 3.00, 0.00
Duration      [total, attack, wait]             5m30s, 5m0s, 30.002s
Latencies     [min, mean, 50, 90, 95, 99, max]  30s, 30.001s, 30s, 30.004s, 30.004s, 30.004s, 30.005s
Bytes In      [total, mean]                     0, 0.00
Bytes Out     [total, mean]                     0, 0.00
Success       [ratio]                           0.00%
Status Codes  [code:count]                      0:900
Error Set:
Get "http://localhost:3000/rest/products/search?q=": context deadline exceeded (Client.Timeout exceeded while awaiting headers)
```

## with-agent-protect

```
Average container CPU% is 44.71 and MEM% is 3.20

Requests      [total, rate, throughput]         900, 3.00, 3.00
Duration      [total, attack, wait]             5m0s, 5m0s, 134.99ms
Latencies     [min, mean, 50, 90, 95, 99, max]  102.839ms, 122.682ms, 118.064ms, 139.916ms, 149.565ms, 195.682ms, 247.768ms
Bytes In      [total, mean]                     11785500, 13095.00
Bytes Out     [total, mean]                     0, 0.00
Success       [ratio]                           100.00%
Status Codes  [code:count]                      200:900
Error Set:
```
