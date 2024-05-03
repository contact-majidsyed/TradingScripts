#### Problem statement

- Simple Reversal bar
     - Previous bar is opposite bar body, so current bar is Reversal bar
        - If Doji, then use the bar before Doji as base (Doji = 0 body)
        - End Result = Color the Reversal Bar chosen Color for BL and BR

#### Code
```
//@version=5
//@version=5
indicator("Simple Reversal Bar")

// this bar
isCurBl = close > open
isCurBr = close < open
isCurDj = close == open

// previous bar
isPrevDj = close[1] == open[1]
isPrevBl = isPrevDj ? close[2] > open[2]: close[1] > open[1]
isPrevBr = isPrevDj ? close[2] < open[2]: close[1] < open[1]
// this bar is reversal ?
isCurBlRv = isCurBl and isPrevBr
isCurBrRv = isCurBr and isPrevBl

// this bar is BL reversal or BR reversal ?
plotcandle(open, high, low, close, title='Strong Bull Reversal', color = isCurBlRv ?  color.green : na)
plotcandle(open, high, low, close, title='Strong Bear Reversal', color = isCurBrRv ?  color.red : na)

```

#### Sample Output
![Output](./output.png)