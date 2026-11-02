# Simple Explanation of ZRAM

Say an app uses 100 MB of RAM. When you go home without closing it, Android keeps it in RAM so it reopens fast.

If you then open another app and RAM gets tight, the kernel compresses the inactive parts of that first app into a section of RAM called ZRAM. The 100 MB might shrink to around 30-40 MB (depends on the data and the compression algorithm), freeing the rest for the new app. Nothing leaves RAM, so it decompresses quickly when you switch back.

ZRAM works like swap, but it lives in compressed RAM instead of on storage. That makes it much faster than a swap file or partition, and it doesn't wear out your flash storage. The trade-off is a bit of CPU time spent compressing.

On phones, ZRAM alone is usually the best choice. Disk-based swap is slower and adds flash wear, so only add it if you know you need it.


(Taken from [https://t.me/ryukinotes/58](https://t.me/ryukinotes/58) but revised for clarity and accuracy)
