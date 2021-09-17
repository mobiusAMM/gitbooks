# GaugeContoller.vy

The contract holds a list of guage types and their corresponding weights. Each guage stores the values of points per vote in the function vote\_points. Below are all changes to the initial gauge controller from the curveDAO. 

```text
@external
def initiateForFarming():
    assert not self.initiated # dev: can only be ran once
    self.initiated = True
    next_time: uint256 = (block.timestamp + WEEK) / WEEK * WEEK
    cur_time: uint256 = (block.timestamp) / WEEK * WEEK
    self.points_total[cur_time] = self.points_total[next_time]
    self.points_total[cur_time] = self.points_total[next_time]
    self.points_type_weight[0][cur_time] = self.points_type_weight[0][next_time]
    self.points_sum[0][cur_time].bias = self.points_sum[0][next_time].bias

    for gauge in self.gauges:
        self.points_weight[gauge][cur_time].bias = self.points_weight[gauge][next_time].bias
    for gauge in self.gauges:
        self._get_weight(gauge)
    self._get_total()
```

