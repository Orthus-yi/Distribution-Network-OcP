# Distribution_Network_Ss
Operation Constraints and Parameter Settings of Distribution Network
## Distribution network operation constraints

### Substation node constraints

$$
P^\text{sub,min}\leq P_{i,t}^\text{sub}\leq P^\text{sub,max},\forall i\in \mathcal{P}_\text{sub},\forall t
$$

$$
Q^\text{sub,min}\leq Q_{i,t}^\text{sub}\leq Q^\text{sub,max},\forall i\in \mathcal{P}_\text{sub},\forall t
$$

$$
\nu_{i,t}=\left(1+\sigma_{i,t}\Delta V\right)^2V^2_{i,\text{rated}}
$$

$$
\sigma^\text{min}\leq \sigma_{i,t}\leq \sigma^\text{max},\forall i\in \mathcal{P}_\text{sub},\forall t
$$

where $Q_{i,t}^\text{sub}$ represents the reactive power output by the substation node at time *t*; $P^\text{sub,min}/P^\text{sub,max}$ and $Q^\text{sub,min}/Q^\text{sub,max}$ denote the upper/lower limits of the active power output and the upper/lower limits of the reactive power output of the substation node, respectively; $\nu_{i,t}$ and $\sigma_{i,t}$ stand for the square of the voltage amplitude at node *i* and the tap position of the on-load tap changer (OLTC) at time *t*, respectively; $\Delta V$, $V_{i,\text{rated}}$, and $\sigma^\text{min}/\sigma^\text{max}$ refer to the voltage variation per tap of the OLTC, the rated voltage, and the upper/lower limits of the tap position, respectively.

### Distributed Generator Constraints:

$$
0\leq P_{i,t}^\text{dg}\leq P_i^\text{dg,max}
$$

$$
-RD_i^\text{dg}\leq P_{i,t+1}^\text{dg}-P_{i,t}^\text{dg}\leq RU_i^\text{dg},\forall i\in \mathcal{P}_\text{dg},\forall t
$$

$$
P_{i,t}^\text{dg}\tan\varphi_i^\text{dg,min}\leq Q_{i,t}^\text{dg}\leq P_{i,t}^\text{dg}\tan\varphi_i^\text{dg,max},\forall i\in \mathcal{P}_\text{dg},\forall t
$$

where $P_i^\text{dg,max}$ and $RU_i^\text{dg}/RD_i^\text{dg}$ represent the upper limit of active power and the upper/lower ramp limits of the distributed generator (DG) at node *i*, respectively; $Q_{i,t}^\text{dg}$ denotes the reactive power of the DG; $\varphi_i^\text{dg,max}/\varphi_i^\text{dg,min}$ stand for the upper/lower limits of the power factor angle of the DG.

### Photovoltaic Equipment Constraints:

$$
P_{i,t}^\text{pv}+P_{i,t}^\text{pv,ct}=P^\text{pv,max}_{i,t}
$$

$$
P_{i,t}^\text{pv},P_{i,t}^\text{pv,ct}\geq 0,\forall i\in \mathcal{P}_\text{pv},\forall t
$$

where $P_{i,t}^\text{pv}$ and $P_{i,t}^\text{pv,max}$ represent the actual active power and the maximum active power of the photovoltaic system at node *i* at time *t*, respectively.

### Wind Turbine Constraints:

$$
P_{i,t}^\text{w}+P_{i,t}^\text{w,ct}=P^\text{w,max}_{i,t}
$$

$$
Q_{i,t}^\text{w}=P^\text{w}_{i,t}\tan\varphi_i^\text{w}
$$

$$
P_{i,t}^\text{w},P_{i,t}^\text{w,ct}\geq 0,\forall i\in \mathcal{P}_\text{w},\forall t
$$

where $P_{i,t}^\text{w}$, $Q_{i,t}^\text{w}$, and $P_{i,t}^\text{w,max}$ represent the actual active power, actual reactive power, and maximum active power of the wind turbine at node *i* at time *t*, respectively; $\varphi_i^\text{w}$ denotes the power factor angle of the wind turbine.

### Energy Storage System Constraints:

$$
-P_i^\text{ess,max}\leq P_{i,t}^\text{ess}\leq P_i^\text{ess,max}
$$

$$
E_{i,t+1}^\text{ess}=E_{i,t}^\text{ess}+\left(\eta_i^\text{ess,c}+1/\eta_i^\text{ess,d}\right)P_{i,t}^\text{ess}\Delta t/2+\left(\eta_i^\text{ess,c}-1/\eta_i^\text{ess,d}\right)\left|P_{i,t}^\text{ess}\right|\Delta t/2
$$

$$
E_{i}^\text{ess,min}\leq E_{i,t}^\text{ess}\leq E_{i}^\text{ess,max},\forall i\in\mathcal{P}_\text{ess},\forall t
$$

$$
E_{i,1}^\text{ess}=E_{i,T}^\text{ess},\forall i\in\mathcal{P}_\text{ess}
$$

where $P_{i,t}^\text{ess}$ and $E_{i,t}^\text{ess}$ represent the active power and energy capacity of the energy storage system at node *i* at time *t*, where $P_{i,t}^\text{ess}>0$ indicates charging and $P_{i,t}^\text{ess}<0$ indicates discharging to the distribution network; $P_{i}^\text{ess,max}$, $E_{i}^\text{ess,max}/E_{i}^\text{ess,min}$, and $\eta_i^\text{ess,c}/\eta_i^\text{ess,d}$ denote the maximum power, maximum/minimum energy capacity, and charging/discharging efficiency of the energy storage system at node *i*, respectively.

### Static Var Compensator Constraints:

$$
Q_i^\text{svc,min}\leq Q_{i,t}^\text{svc}\leq Q_i^\text{svc,max},\forall i\in\mathcal{P}_\text{svc},\forall t
$$

where $Q_{i,t}^\text{svc}$ and $Q_i^\text{svc,max}/Q_i^\text{svc,min}$ represent the reactive power output and the upper/lower limits of reactive power of the static var compensator at time *t*, respectively.

### Node Voltage and Line Current Constraints:

$$
V_{i,\text{min}}^2\leq \nu_{i,t}\leq V_{i,\text{max}}^2,\forall i\in\mathcal{P}_\text{N},\forall t
$$

$$
0\leq \ell_{ij,t}\leq I_{ij,\text{max}}^2,\forall ij\in\mathcal{P}_\text{line},\forall t
$$

where $V_{i,\text{max}}/V_{i,\text{min}}$ and $I_{ij,\text{max}}$ represent the upper/lower voltage limits of node *i* and the upper current limit of line *ij*, respectively; $\mathcal{P}_\text{N}$ denotes the set of all distribution network nodes.

### AC Power Flow Constraints

$$
\sum\limits_{j\in \varsigma_{i}} P_{ij,t} = P_{i,t}^{\text{sub}} + P_{i,t}^{\text{dg}} + P_{i,t}^{\text{pv}} + P_{i,t}^{\text{w}} - P_{i,t}^{\text{ess}} - P_{i,t}^{\text{cs}} - P_{i,t}^{\text{ld}} \left(1-\delta_{i,t}^{\text{ct}}\right) + \sum\limits_{k\in \vartheta_{i}} \left( P_{ki,t} - R_{ki} \ell_{ki,t} \right),\quad \forall i\in \mathcal{P}_{\text{N}},\forall t
$$

$$
\sum\limits_{j\in \varsigma_{i}} Q_{ij,t} = Q_{i,t}^{\text{sub}} + Q_{i,t}^{\text{dg}} + Q_{i,t}^{\text{w}} + Q_{i,t}^{\text{svc}} - Q_{i,t}^{\text{ld}} \left(1-\delta_{i,t}^{\text{ct}}\right) + \sum\limits_{k\in \vartheta_{i}} \left( Q_{ki,t} - X_{ki} \ell_{ki,t} \right),\quad \forall i\in \mathcal{P}_{\text{N}},\forall t
$$

$$
\nu_{i,t} - \nu_{j,t} = 2 \left( R_{ij} P_{ij,t} + X_{ij} Q_{ij,t} \right) - \left( R_{ij}^{2} + X_{ij}^{2} \right) \ell_{ij,t},\quad \forall ij\in \mathcal{P}_{\text{line}},\forall t
$$

$$
\ell_{ij,t} \nu_{i,t} - P_{ij,t}^{2} - Q_{ij,t}^{2} = 0,\quad \forall ij\in \mathcal{P}_{\text{line}},\forall t
$$

where $P_{ij,t}$, $Q_{ij,t}$, and $X_{ij}$ represent the active power, reactive power, and reactance of the $ij$ line, respectively; $\varsigma_{i}$ and $\vartheta_{i}$ denote the set of child nodes and parent nodes of node $i$, respectively; and $Q_{i,t}^{\text{ld}}$ stands for the reactive power of the load at node $i$ at time $t$. 

## Parameters of Distribution Network Resources

| Equipment Parameter                                          | Value  | Equipment Parameter                                          | Value |
| ------------------------------------------------------------ | ------ | ------------------------------------------------------------ | ----- |
| Upper Limit of Node Voltage (p.u.)                           | 1.07   | Energy Storage System Capacity (MWh)                         | 1.5   |
| Lower Limit of Node Voltage (p.u.)                           | 0.93   | Lower Limit of Energy Storage System Charge (MWh)            | 0.15  |
| Line Model                                                   | LGJ-95 | Initial Charge of Energy Storage System (MWh)                | 0.9   |
| Maximum Allowable Current of Line (A)                        | 335    | Maximum Value of Static Var Compensator (Mvar)               | 0.6   |
| Substation Capacity (MVA)                                    | 10     | Minimum Value of Static Var Compensator (Mvar)               | -0.2  |
| Maximum Adjustment Times of On-load Tap Changer              | 6      | Curtailment Price of Photovoltaic Power (CNY/(MWh))          | 100   |
| Tap Position of On-load Tap Changer                          | 12     | Curtailment Price of Wind Power (CNY/(MWh))                  | 100   |
| Upper Limit of Active Power of Distributed Generator (MW)    | 0.5    | Curtailment Price of Load (CNY/(MWh))                           | 500   |
| Upper Limit of Reactive Power of Distributed Generator (Mvar) | 0.25   | Network Loss Price (/(MWh))                                          | 50    |
| Upper Limit of Ramp Rate of Distributed Generator (MW)       | 0.15   | Time Granularity of Equipment Power in Distribution Network (min) | 15    |
| Upper Limit of Charging and Discharging Power of Energy Storage System (MW) | 0.3    | Time Granularity of Pricing Strategy of Charging Station Cooperative Alliance (h) | 1     |
| Charging and Discharging Efficiency of Energy Storage System | 0.9381 | Total Simulation Period (h)                                  | 24    |
