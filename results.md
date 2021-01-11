# PERF RESULTS

command:
```
echo 'GET http://localhost:3000/rest/products/search?q=' | vegeta attack -rate=3/s -duration=5m -name=without-agent -output=without-agent.bin

echo 'GET http://localhost:3000/rest/products/search?q=' | vegeta attack -rate=3/s -duration=5m -name=with-agent-assess -output=with-agent-assess.bin

echo 'GET http://localhost:3000/rest/products/search?q=' | vegeta attack -rate=3/s -duration=5m -name=with-agent-protect -output=with-agent-protect.bin
```

## without-agent

```
Average container CPU% is 9.88 and MEM% is .87

Requests      [total, rate, throughput]         900, 3.00, 3.00
Duration      [total, attack, wait]             5m0s, 5m0s, 21.23ms
Latencies     [min, mean, 50, 90, 95, 99, max]  15.284ms, 22.004ms, 22.085ms, 24.75ms, 26.145ms, 29.881ms, 38.006ms
Bytes In      [total, mean]                     12033900, 13371.00
Bytes Out     [total, mean]                     0, 0.00
Success       [ratio]                           100.00%
Status Codes  [code:count]                      200:900
```

## with-agent-assess

```
Average container CPU% is 46.17 and MEM% is 1.45

Requests      [total, rate, throughput]         900, 3.00, 3.00
Duration      [total, attack, wait]             5m0s, 5m0s, 117.599ms
Latencies     [min, mean, 50, 90, 95, 99, max]  105.672ms, 119.577ms, 116.761ms, 124.758ms, 129.33ms, 209.798ms, 264.444ms
Bytes In      [total, mean]                     12033900, 13371.00
Bytes Out     [total, mean]                     0, 0.00
Success       [ratio]                           100.00%
Status Codes  [code:count]                      200:900
```

## with-agent-protect

```
Average container CPU% is 15.12 and MEM% is 1.22

Requests      [total, rate, throughput]         900, 3.00, 3.00
Duration      [total, attack, wait]             5m0s, 5m0s, 35.491ms
Latencies     [min, mean, 50, 90, 95, 99, max]  27.367ms, 36.226ms, 36.084ms, 39.164ms, 40.618ms, 46.087ms, 82.345ms
Bytes In      [total, mean]                     12033900, 13371.00
Bytes Out     [total, mean]                     0, 0.00
Success       [ratio]                           100.00%
Status Codes  [code:count]                      200:900
```
