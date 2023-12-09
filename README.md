
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


Below image shows the multi-voltage design, where we reduce the voltage in lower performance blocks.


<img width="72" alt="Multi-Voltage" src="https://github.com/SATYASAIKRISHNA9/UPF-RELATED-REPO/assets/79971687/0ed63e5a-8693-46a3-b4f2-ed57cf6f275a">


Below image represents MTCMOS (POWER GATING) concept, in which we cut off the power to some blocks which we do not need them for a certain time. (Here we are reducing the leakage power).


<img width="78" alt="snip2" src="https://github.com/SATYASAIKRISHNA9/UPF-RELATED-REPO/assets/79971687/68a1d120-1910-4714-94e5-18c618ffc152">


Next image belongs to combination of Multi-voltage and POWER GATING concept with state retention


<img width="73" alt="snip3" src="https://github.com/SATYASAIKRISHNA9/UPF-RELATED-REPO/assets/79971687/a47e0ee8-c0fa-4ce8-8c6f-f891365ca5d9">


### Power Gating


Power gating is shutting down a portion of design from the (always-on/alive) portion of design. The cells which are communicating to alive portion of design may produce crow bar currents and may manupulate the data. Thats why we need to use isolation cells where communication is going from shut down portion to the alive portion of the design.



