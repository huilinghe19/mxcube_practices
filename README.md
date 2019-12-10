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



