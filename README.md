# mxcube_practices

My Work
----------------------------------------------------------------------------------------------------------------------------

1.  

   The pseudo control PID parameters are changed to make the motors move stable. The values are shown in the image "pid_parameters.png". 

   The main point is that, the D(differemtial control) parameter should be 0. Because this is usually used for controlling of the objects with hysteresis, such as temperature control. In motion control D parameter is not used, if we set D parameter too much, the response process will be braked in advance and the adjust time will be extended. 
  
  As for the P and I parameters, In fact, P can be set in the area of 0.3-0.7, we choose 0.5. D can be set in the area of 0.4-3, we choose 1.0. These parameters are not tested to be the perfect ones, they can be only the availble ones. 
  
  If problems of the motors happens, please change the velocity lower. PID control may not be the problems then. 
