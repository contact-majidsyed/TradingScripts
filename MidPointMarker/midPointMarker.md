
#### Problem statement: 
Marks 2 mid points for each bar
 - Midpoint one - between open and close
- Midpoint two - between high and low

#### Code
```
// This Pine Script™ code is subject to the terms of the Mozilla Public License 2.0 at https://mozilla.org/MPL/2.0/

//@version=5
indicator("Mid point indicator", overlay = true)
openCloseMidpoint = 0.5 * (open +close)
highLowMidpoint = 0.5 * (high +low)
//  plotshape(openCloseMidpoint, style=shape.circle, location = location.absolute, color = color.red)
// plotshape(highLowMidpoint, style=shape.flag, location = location.absolute, color = color.green)

plotchar(openCloseMidpoint, "openCloseMidpoint", "-", location.absolute, color = color.red)
plotchar(highLowMidpoint, "highLowMidpoint", "-", location.absolute, color = color.green)
```

### Sample Output


![alt](./midPointMarker_updated.png)