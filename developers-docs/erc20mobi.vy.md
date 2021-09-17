# ERC20MOBI.vy

## Supply parameters

The initial supply will 660,000,000 tokens 

```
INITIAL_SUPPLY: constant(uint256) = 660_000_000
INITIAL_RATE: constant(uint256) = 274_815_283 * 10 ** 18 / YEAR  # leading to 43% premine
RATE_REDUCTION_TIME: constant(uint256) = YEAR
RATE_REDUCTION_COEFFICIENT: constant(uint256) = 18181818181818181818  # 100 / 55 = 1.818...
RATE_DENOMINATOR: constant(uint256) = 10 ** 18
INFLATION_DELAY: constant(uint256) = 0 #86400
```

{% hint style="info" %}
 Once deployed, the supply parameters in ERC20MOBI.vy contract cannot be changed.
{% endhint %}

