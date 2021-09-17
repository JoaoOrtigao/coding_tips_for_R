Saving DESeq2 objects
================
Joao Ortigao - R version 4.0.5 (2021-03-31)
2021-08-07

A nice way to save DESeq2 objects is with the function saveRDS(), which
can save a binary file from your object. By default this function
compress the data using the gzip format. Let’s check how to use it…

``` r
saveRDS(rld,"rld.gz.rds")
```

Now let’s see how to bring back the object to the memory. As the
function saveRDS() compact the data by default, we need to use a
function to decompress your object before bringing it to memory.

``` r
con <- gzfile("rld.gz.rds")
rld <- readRDS(con)
close(con)
```

Have fun!
