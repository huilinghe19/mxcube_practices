# mxcube_practices

My Work
----------------------------------------------------------------------------------------------------------------------------
Recent work: use Lima und Blissgarten to controll the detector camera MarCCD. http://lima.blissgarden.org/camera/marccd/doc/index.html

1. my first protocol for the development meeting MX-Group (Protokoll 10.01.2019) https://www.bessy.de/mxwiki/doku.php?id=psf:hard_and_software_development_meeting


2. PID controll parameters setting
2.1 PID Controller


PID Controller is used to decrease the error. Once the result is not equal the expected value, then PID controller works.

The P controller works to decrease the error at once. P parameter higher, the ajust time lower. But the p parameter can not be too high, otherweise the system will be unstable. 

The I controller works to elimate the steady stable error. I parameter higher, the ajust time lower. But the I parameter can not be too high, otherweise the system will be unstable. 

The D controller works to predict the trend of error changes in advance and decrease the hysteresis effect. 


2.2 Pseudo control PID parameters configuration


   The pseudo control PID parameters are configured to make the motors move stable. The values are shown in the image "pid_parameters.png". 

   The main point is that, the D(differemtial control) parameter should be 0. Because this is usually used for controlling of the objects with hysteresis, such as temperature control. In motion control D parameter is not used, if we set D parameter too much, the response process will be braked in advance and the adjust time will be extended. 
  
  As for the P and I parameters, In fact, P can be set in the area of 0.3-0.7, we choose 0.5. D can be set in the area of 0.4-3, we choose 1.0. These parameters are not tested to be the perfect ones, they can be only the availble ones. 
  
  If problems of the motors happens, please change the velocity lower. PID control parameters may not be the problem then. 
