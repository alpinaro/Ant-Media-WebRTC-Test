WebRTCTest Tool is a java project for testing Ant Media Server webrtc capabilities.

* WebRTCTest is compatiple with Ant Media Server signalling protocol. 
* There is two modes of WebRTCTest: publisher and player. (-m flag determines the mode)
* WebRTCTest two options with UI or without UI. (-u flag determines the UI od/off)
* You can save recieved(in player mode) or published(in publisher mode) frames as png. (-p flag determines the saving periof of frames. If you set 100 it saves every 100 frames.)

## Run
It can be run from command promt with the following options.
```
./run.sh -f output.mp4 -m publisher -n 1 -s 10.10.175.53  #publishes output.mp4 to the server with default name myStream
```

```
./run.sh -m player -n 100 -i stream1 -s 10.10.175.53 -u false #plays 100 viewers for default stream myStream
```

### Parameters
```
Flag 	 Name      	  Default   	 Description                 
---- 	 ----      	  -------   	 -----------   
f    	 File Name 	  test.mp4     Source file* for publisher output file for player        
s    	 Server IP 	  localhost 	 server ip                   
q    	 Security  	  false     	 true(wss) or false(ws)      
l        Log Level      3           0:VERBOSE,1:INFO,2:WARNING,3:ERROR,4:NONE
i    	 Stream Id 	  myStream  	 id for stream               
m    	 Mode      	  player    	 publisher or player         
u    	 Show GUI  	  true      	 true or false               
p    	 Port      	  5080      	 websocket port number 
v    	 Verbose   	  false     	 true or false 
n    	 Count     	  1         	 Number of player/publisher connctions 
k         Kafka Broker  null        Kafra broker address with port
r    	 Publish Loop  false       true or false
c    	 Codec         h264        h264, VP8 or h265 
d    	 Data Channel  false       true or false 
```

*File should be in mp4 format and h264, opus encoded