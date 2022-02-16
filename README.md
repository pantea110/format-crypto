# format-crypto

## Value format testcases
### Stables -> 2f
```
       ff
[01] 1.000000000000000000 DAI -> 1.00
[02] 1 DAI -> 1.00
[03] 0.100000000000000000 DAI -> 0.10
[04] 0.1 DAI -> 0.10

       ff
[05] 1.1 DAI -> 1.10
[06] 1.11 DAI -> 1.11
[07] 1.111 DAI -> 1.11

       ff
[08] 1.5 DAI -> 1.50
[09] 1.15 DAI -> 1.15
[10] 1.115 DAI -> 1.12
[11] 1.1115 DAI -> 1.11

        ff
[12] 99.9 DAI -> 99.90
[13] 99.99 DAI -> 99.99
[14] 99.999 DAI -> 100.00
[15] 99.9999 DAI -> 100.00
```

### Not stables -> 6f
```
       ffffff
[16] 1.000000000000000000 ETH -> 1.00
[17] 1 ETH -> 1.00
[18] 0.100000000000000000 ETH -> 0.10
[19] 0.1 ETH -> 0.10

       ffffff
[20] 0.10001 ETH -> 0.10001
[21] 0.100001 ETH -> 0.100001
[22] 0.1000001 ETH -> 0.10
[23] 0.10000001 ETH -> 0.10

       ffffff
[24] 0.10005 ETH -> 0.10005
[25] 0.100005 ETH -> 0.100005
[26] 0.1000005 ETH -> 0.100001
[27] 0.10000005 ETH -> 0.10

       ffffff
[28] 0.99999 ETH -> 0.99999
[29] 0.999999 ETH -> 0.999999
[30] 0.9999999 ETH -> 1.00
[31] 0.99999999 ETH -> 1.00
```

### Fiat -> 2f
```
[32] 12.3456 USD -> 12.35
```

### Fiat, 0.00... -> 6f | (?) Fiat, < 0.004(9)
```
[33] 0.004 USD -> 0.004
[34] 0.00401 USD -> 0.00401
[35] 0.005 USD -> 0.005
[36] 0.0005 USD -> 0.0005
[37] 0.000500001 USD -> 0.0005
[38] 0.0011111 USD -> 0.001111
[39] 0.0012345 USD -> 0.001235
```

### Fiat todo:
```
$0.001 -> ?
$0.0001 -> ?
$0.00001 -> ?
$0.000001 -> ?
$0.0000001 -> ?
$0.005 -> ?
$0.0005 -> ?
$0.00005 -> ?
$0.000005 -> ?
$0.0000005 -> ?
$0.99 -> ?
$0.999 -> ?
$0.9999 -> ?
$0.99999 -> ?
$0.999999 -> ?
$0.9999999 -> ?
```

### Big values
```
[40] 10 ETH -> 10.00 ETH
[41] 10.1234567890 ETH -> 10.12 ETH
[42] 10 DAI -> 10.00 DAI
[43] 10.1234567890 DAI -> 10.12 DAI
```

### Special cases
```
[44] undefined ETH -> undefined
[45] Infinity ETH -> ∞
[46] -Infinity ETH -> -∞
[47] NaN -> ''
```
