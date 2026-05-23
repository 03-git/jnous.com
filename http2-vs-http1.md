title: HTTP/2 vs HTTP/1.1
summary: HTTP/2 multiplexing delivers 2.1x throughput for local inference concurrency. 70 validated measurements, gemma-4-26B-A4B on Apple Silicon.
date: 2026-04-25
url: https://jnous.com/http2-vs-http1.md
source: production empirical (70 measurements, 3 conditions, gemma-4-26B-A4B, M1 Max 64GB)
license: GPLv2


HTTP/2 VS HTTP/1.1 FOR LOCAL INFERENCE

RESULT

       Local inference server (llama-server) behind HTTP/2 multiplexing
       delivers 2.1x aggregate throughput versus HTTP/1.1 at equivalent
       concurrency.

       70 validated measurements across 3 conditions. Same model, same
       hardware, same prompts. The only variable is the wire protocol.

WHY

       HTTP/1.1 serializes requests per connection. Multiple concurrent
       inference requests queue behind each other. Opening multiple
       connections works around this but adds overhead per connection.

       HTTP/2 multiplexes streams over a single connection. Concurrent
       requests interleave on the wire. The inference server processes
       them in parallel without connection overhead.

       The bottleneck for local inference at concurrency > 1 is not
       compute — it's the wire protocol blocking concurrent delivery.

DATA
       github.com/03-git/variance-lab findings/07-http2-vs-http1.txt
