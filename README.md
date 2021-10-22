# Sending-SCD30-sensor-data-to-a-network-server-via-LoRaWAN-protocol-

                                             /***** Sending data to a network server via LoRaWAN protocol *****/ 
                                             *******************************************************************

                                           /// This project was built using STM32CubeIDE with HAL librairies ///


To use this driver, you must import the project named LoRaWAN_End_Node from STM32WL firmware then you ought to activate I2C communication and generate the code.

The STM32WL board communicates with the SCD30 sensor via I2C.


-- Procedure  ::

First of all, go to app_lora.c and copy the content of this driver ( don't you forget to add SCD30_sensor.h ).
you can visualize data to be sent in the terminal.

after configuring your Gateway and adding the suitable DevEUI and APPKey to your network server ( Loriot / CAYENNE ) you can verify that your device join
the server.



-- About LoRaWAN configuration :: 

    -*- OTAA :  Over The Air Activation  &&&   ABP : Activation By Personnalization -*- 
          -*- OTAA or APB are used to connect the device to the network server ---- OTAA is the most secure so it is the most prefered -*-
    -*- DEVEUI : Device MAC address   
    -*- APPEUI : Uniquely identifies the application server ( port number )
    -*- APPKEY : is an AES ( Advanced Encryption Standard ) 128 bit :: root key ( Both end device and the network server must have the same APPKEY 
          -*- EUI  stands for Extended Unique Identifier -*-
                          
-- About the sensor SCD30 :: 
                 
                 

                   Sensor address ( 7 bits )            ::  0x61 
                   Sensor address with read argument:1  ::  0xC3
                   Sensor address with write argument:0 ::  0xC2
                   Command that starts measurement      ::  0x0010 
                   Command that gets  ready status      ::  0x0202
                   Command that reads measurement       ::  0x0300




-- I2C1 connection :: 
 

                           SCD30 SENSOR    ||    STM32WL
                       ---------------------------------------
                              VIN                 3.3V
                              GND                 GND 
                              SDA                 PB7
                              SCL                 PB8
                      -----------------------------------------
