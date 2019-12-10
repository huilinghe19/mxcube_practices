# mxcube_practices

----------------------------------------------------------------------------------------------------------------------------
Recent work:
---------------------------------------------------------
Mxcube3

Steps:


    Getting mxcube: (put it somewhere you like, do not use you existing mxcube3 folder)

        git clone https://github.com/meguiraun/mxcube3.git
        cd mxcube3
        git checkout -b v3.0.1 origin/v3.0.1
        cd mxcube3
        git clone https://github.com/meguiraun/HardwareRepository.git
        cd HardwareRepository
        git checkout -b 2.2 origin/2.2
         
         

    Running: change the firt part of the -v to where you downloaded mxcube3 in the step above
    docker pull mikeleguiraun/mxcube:mxcube3_workshop

    Terminal1: docker run -v <YOUR_PATH_TO_MXCUBE>:/mxcube/mxcube3 -p 8081:8081 -p 8090:8090 --name mxcube3_workshop  mikeleguiraun/mxcube:mxcube3_workshop
    Terminal2:  docker exec -it mxcube3_workshop  python mxcube3-server -w True -r test/HardwareObjectsMockup.xml
    Terminal3:   docker exec -it mxcube3_workshop  npm install -> this is only needed once, it takes a while
    Terminal3: docker exec -it mxcube3_workshop  npm start (leave this running all the time)
     

    go to localhost:8090, username: idtest0, whatever password
     

    For getting into the container: docker exec -it mxcube3_workshop /bin/bash

The mxcube3 is open in the web. See the "images/mxcube3_1.png".


Future work:
---------------------------------------------------------
use Lima und Blissgarten to controll the detector camera MarCCD. http://lima.blissgarden.org/camera/marccd/doc/index.html


Finished Work
-----------------------------------------------------------
  
  
 SmarAct Tango Device Server 


1. My first protocol for the development meeting MX-Group (Protokoll 10.01.2019) https://www.bessy.de/mxwiki/doku.php?id=psf:psf.hsdm_minutes_2019-01-10



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
