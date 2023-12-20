

# UPF-RELATED-REPO
This repo gives information on UPF

### AFTER GOING THROUGH THIS REPO WE CAN DO FOLLOWING 
  ==> Describe and identify a power domain 

  
  ==> Describe what power strategies are

  
  ==> Describe how the supply network of a design can be built
      (Create a simple power domain based isolation or retention, or level-shifter strategy)

      
  ==> Use some of UPF power related commands 

## Introduction to UPF
  ==> Complexity of the UPF can no longer be understood unless it is seperated from a design itself

  ==>Power intent in these days are developed along with the functional intent of the design (Both built in parallel)

  ==>UPF represent power intent of the design across the flow (across simulation, verification and implementation)

### Advanced low power techniques


<img width="483" alt="SNIP1" src="https://github.com/SATYASAIKRISHNA9/UPF-RELATED-REPO/assets/79971687/ea652410-5d7c-4b8f-ac68-7ffb55637852">


##### Above picture represents the different types of designs. In the following chapters we are going to discuss about it.


### Below image shows the multi-voltage design, where we reduce the voltage in lower performance blocks.


<img width="72" alt="Multi-Voltage" src="https://github.com/SATYASAIKRISHNA9/UPF-RELATED-REPO/assets/79971687/0ed63e5a-8693-46a3-b4f2-ed57cf6f275a">

We do not require for complete design to work on same voltage as like we dont require all the design to be in same/equal performance. 

##### Note : for higher performance we need higher voltage and less performance we can use less voltage cells. So, static power will get reduced.
 

### Below image represents MTCMOS (POWER GATING) concept, in which we cut off the power to some blocks which we do not need them for a certain time. (Here we are reducing the leakage power).


<img width="78" alt="snip2" src="https://github.com/SATYASAIKRISHNA9/UPF-RELATED-REPO/assets/79971687/68a1d120-1910-4714-94e5-18c618ffc152">


### Next image belongs to combination of Multi-voltage and POWER GATING concept with state retention


<img width="73" alt="snip3" src="https://github.com/SATYASAIKRISHNA9/UPF-RELATED-REPO/assets/79971687/a47e0ee8-c0fa-4ce8-8c6f-f891365ca5d9">


### Power Gating


Power gating is shutting down a portion of design from the (always-on/alive) portion of design. The cells which are communicating from shut-down portion to alive portion of design may produce crow bar currents and may manupulate the data. Thats why we need to use isolation cells where communication is going from shut down portion to the alive portion of the design.

Here we will also use retention cells to retain the previous data.


Below picture represents the power gating cell design. Usually it is large in size.

<img width="255" alt="3" src="https://github.com/SATYASAIKRISHNA9/UPF-RELATED-REPO/assets/79971687/d6e37cfb-a101-47cd-bd44-89a996713149">


#### Note: - Please note that shut down logic will drive the logic or produce crow bar currents and corrupt the data. So, always we need to use isolation cells for power gating cells to drive the logic from power gated portion to the non - power gated portion.



### LOW VDD STANDY


Here we do not want to shut down portion of block, because of dont want to get in headache of extra retention and extra cells [power gating cells]. So, we are going to supply sufficient voltage for the cells in that portion to stand by the data.


## Introduction to UPF: Multi-Voltage


  We do not need all the blocks of a chip operate at same voltage or all the function requires same level of performance.


  For example  ------->   USP vs Processor 


  Processor works on a higher speed. So, the processor needs to work with higher speed as fast as semi-conductor tenchnology can allow. USP works with a low performance. So, we can fix USP with a low voltage.


  <img width="543" alt="4" src="https://github.com/SATYASAIKRISHNA9/UPF-RELATED-REPO/assets/79971687/ac228804-a871-4a38-a4d6-c87f6c55cd81">

`````````````````````````
In the above picture the flow starts with RTL and UPF. But both are designed and handled seperately for future modifications. Initial UPF file consists 
1.  Creation of supply pairs (i.e. supply ports and supply nets).
2.  Definition of power domains and elements in it.
3.  Net connectivity between power domains.
``````````````````````````

Design/Fusion compiler will read RTL and UPF file and generates -->  1. Synthesized netlist   &    2. UPF


UPF generated from the synthesis stage having information of estimated special cells (level shifters, isolation cells) and connectivity in the interfaces of power domains (operating with different voltage).


Later these generated synthesized netlist and upf read by IC Compiler 2 or Fusion Compiler and generates the PGNetlist and UPF


PGNetlist -->  Consists of power rails and ground rails information along with the network connectivity of std cells.


UPF ----> Consists of network connectivity between power domains, std cells placed w.r.t. power domain, Isolation cells and level shifter connectivity with the interfacing nets etc........





### Power Domain Elements

``````````````````````````````````
1.  Power Domains will be operating at different voltages.
2.  Power Domains may ON (OR) OFF depends on the logic and performance (in simple behaviour of their primary supplies).
3.  It requires special cells (power management cells) in the interfaces of power domains (operating with different voltages)
```````````````````````````````````

<img width="271" alt="5" src="https://github.com/SATYASAIKRISHNA9/UPF-RELATED-REPO/assets/79971687/0a561818-fd62-4800-9ef9-4f42d070b75e">




