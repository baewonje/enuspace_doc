---
layout: default
title: BetaInv
parent: Statistics functions
grand_parent: Math & Statistics
last_modified_date: now
---

# BetaInv

Ensor.BetaInv\(Ensor\* pEnsor, double alpha,double beta \)

Ensor.BetaInv\(Ensor\* pEnsor, double alpha,double beta,double A,double B \)

#### Parameters

* Ensor\* pEnsor

Ensor.new\(\) 함수등에 의해 만들어진 포인터를 입력합니다\(0 &lt;= p &lt;= 1\).

* double alpha

베타 분포의 alpha 값을 입력합니다.

* double beta

베타 분포의 beta 값을 입력합니다.

* double A

A : Low Limit 값을 입력합니다. 없으면 0으로 설정됩니다.

* double B

B : High Limit 값을 입력합니다. 없으면 1로 설정됩니다.

#### Return Value

Ensor\* pRetEnsor : pEnsor의 엘리먼트에 맞는 갯수만큼 계산된 Ensor\*를 반환합니다.

#### Remarks

* **CDF**

![](./StatisticsAPI/BetaDistFunc4.png)

![](./StatisticsAPI/BetaDistFunc6.png)

![](./StatisticsAPI/BetaDistFunc7.png)

![](./StatisticsAPI/BetaDistFunc2.png)

#### Examples1

```lua
function MathEquation()
     local ensor_x = ensor.new("{0.05,0.1,0.15,0.2,0.25,0.3,0.35,0.4,0.45,0.5,0.55,0.6,0.65,0.685470581,0.7,0.75,0.8,0.85,0.9,0.95,0.999}")
     local ensor_y = ensor.BetaInv(ensor_x,8,10)
     local ensor_y2 = ensor.BetaInv(ensor_x,8,10,1,3)

     ensor.Plot(ensor_x, ensor_y)
     ensor.Plot(ensor_x, ensor_y2)
     ensor.Table(ensor_y)
     ensor.Table(ensor_y2)
end
```

#### Result

![](./StatisticsAPI/BetaInvResultSample.png)

