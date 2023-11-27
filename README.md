# secret.santa


```R
pool <- seq_len(12)
tst <- FALSE
i <- 0
while(!tst) {
  x <- cbind(pool, sample(pool), sample(pool))
  tst <- all(apply(x, 1, \(.x) length(unique(.x))) == 3)
  i <- i + 1
  print(i)
}



## first successful pool
firstx <- structure(c(1L, 2L, 3L, 4L, 5L, 6L, 7L, 8L, 9L, 10L, 11L, 12L, 
8L, 3L, 5L, 10L, 1L, 4L, 12L, 7L, 2L, 9L, 6L, 11L, 10L, 12L, 
1L, 7L, 3L, 5L, 4L, 2L, 11L, 6L, 9L, 8L), dim = c(12L, 3L), dimnames = list(
    NULL, c("pool", "", "")))

## put in the curly braces for the first adults indexed to write the names in : 
glue::glue({
"
Dear adults[firstx[,1]], you have been assigned two people for Secret Santa!

{adults[firstx[,2]]} and {adults[firstx[,3]]}.

Please gift just these two adults for xmas day. 

There are twelve adults in the Secret Santa pool. Your name has also been discreetly assigned to two other adults.

(No pressure on the gifts, just choose something that works for you). 

Please respond that you got this message and agree to accept this vitally important Xmas mission.

Happy December!

Secret Santa
"

})
```
