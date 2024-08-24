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
  - name: dx
    value: 10
    min: -10
    max: 20
    round: 0.01
  - name: dy
    value: 10
    min: -10
    max: 20
    round: 0.01
calcs:
  db: "-params.dx/params.dy"
layout:
  OneGraph:
    graph:
      objects:
      - EconLinearEquilibrium:
          demand:
            name: ourDemand
            xIntercept: params.dx
            invSlope: calcs.db
          supply:
            name: ourSupply
            yIntercept: 1
            slope: 1
          equilibrium:
            droplines:
              vertical: Q_0
              horizontal: P_0
      - Point:
          coordinates: [params.dx, 0]
          drag:
            - horizontal: dx
      - Point:
          coordinates: [0, params.dy]
          drag:
            - vertical: dy


</div>
