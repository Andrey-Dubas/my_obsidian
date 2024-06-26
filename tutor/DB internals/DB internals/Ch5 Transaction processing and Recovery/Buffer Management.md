#buffer_pool #eviction #page_cache
Cached pages available in memory can be reused under assumption that no other process has modified the data on disk.
Uncached pages are said to be *paged in* when they are loaded from  the disk. If any change is made to the cached page, it is said to be **dirty**. until these pages are **flushed back** on disk.
Since the memory region where cached pages are held is substantially smalled than the whole disk, the page eventually fills up and, in order to **page in** a new page, one of the cached pages has to be **evicted**.