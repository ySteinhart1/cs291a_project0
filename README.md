# cs291a_project0

https://ysteinhart1.github.io/cs291a_project0/

| Concurrency      | Requests Served with HTTPS| 
| ----------- | ----------- | 
| 2      | 248       |
| 4   | 466        |
| 8   | 1007       |
| 16   | 1811       | 
| 32   | 2269       |
| 64   | 2666       |
| 128   | 2596       |
| 256   | 2624       |

* There are diminishing returns since the server is not able to scale endlessly. For each concurrent request, it has to spin off a thread to handle it. At a certain point, the server is spinning off more threads than it is able to linearly scale with, so the cost of each thread becomes greater. Once we reach this point, it is limited by the number of concurrent requests it can handle, so even if more requests are issued, it is still limited by the ability of the server to respond to these requests.

* HTTP performs much better than HTTPS for lower values of concurrency, but once it grows large enough, the lower connection time is dwarfed by the overhead of responding to all of the concurrent threads.

* Github is able to respond quickly likely because they scale their pages to support concurrent requests and distributes static resources to be physically closer using CDNs.

* PageSpeed Insights shows my Time to Interactive at 0.4 s
