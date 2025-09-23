# index
## a
* 1
* 2
* 3

```haskell
modPow :: ModInt -> Int  -> ModInt
modPow a n = fst $ foldl f (1, a) ns
    where
        f (res, a') n'
            | n' == 1 = (res * a', a'')
            | otherwise = (res, a'')
            where
                a'' = a' * a'
        ns = map (`mod` 2) . takeWhile (> 0) . iterate (`div` 2) $ n
```
