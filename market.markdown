---
layout: default
title: "Market Forces: Demand and Supply"
permalink: /market-forces/
---

* **Demand** is the quantity of a good that consumers are willing and able to purchase at various prices during a given time.
* **Supply** is ...

<div class="kg-container">

schema: EconSchema
params:
- name: demandShift
  value: 0,
  min: -2
  max: 2
  round: 0.1
- name: demandRotation
  value: 0
  min: -1
  max: 1
  round: 0.1
- name: supplyShift
  value: 0
  min: -2
  max: 2
  round: 0.1
- name: supplyRotation
  value: 0
  min: -1
  max: 1
  round: 0.1
layout:
  OneGraph:
    graph:
      objects:
      - EconLinearEquilibrium:
          name: ourEquilibrium
          demand:
            name: ourDemand
            xIntercept: 8 + params.demandShift
            invSlope: -1 + params.demandRotation
            drag:
            - horizontal: demandShift
            - vertical: demandRotation
          supply:
            name: ourSupply
            yIntercept: 1 - params.supplyShift
            slope: 1 + params.supplyRotation
            drag:
              - horizontal: supplyShift
              - vertical: supplyRotation
          equilibrium:
            droplines:
              vertical: "`Q_0 = ${calcs.ourEquilibrium.Q.toFixed(2)}`"
              horizontal: "`P_0 = ${calcs.ourEquilibrium.P.toFixed(2)}`"

</div>
