##SDK Version : ESP8266_RTOS_SDK_V1.4.2_16_07_04
##Platform : ESP-LAUNCHER BAOARD

##Operation Steps:

1. Enter path:/home/esp8266/Share, clone ESP8266 RTOS SDK to lubuntu environment by command: 
       
		git clone https://github.com/espressif/ESP8266_RTOS_SDK.git 
	   
2. Enter SDK folder:/home/esp8266/Share/ESP8266_RTOS_SDK, Copy example folder "UDP_Server_Demo" next to bin/ folder in the SDK folder. The SDK folder should have folders inside it like : bin, examples, third party...

3. If the SDK path is not updated in gen_misc.sh, right click the script and edit the path to bin folder and SDK folder. for the current SDK, the gen_mish.sh would have a path like:
       
		export SDK_PATH="/home/esp8266/Share/ESP8266_RTOS_SDK"
		export BIN_PATH="/home/esp8266/Share/ESP8266_RTOS_SDK/bin"
	   
4. Enter example folder, run ./gen_misc.sh, and follow below steps to fininsh the sample code compile:
	
		Option 1 will be automatically selected, 
		Option 2 > Enter 1. 
		Option 3 > Enter Default(Just Press enter)
		Option 4 > Enter Default(Just Press enter)
		Option 5 > Enter 5.
	   
5. "user1.2048.new.5.bin" should be found in "/home/esp8266/Share/ESP8266_RTOS_SDK/bin/upgrade", Flash the Binaries with ESP Flashing tool at the instructed Locations. Download bin files to ESP-LAUNCHER as below sittings.
		
		Download address of each bin files:
		blank.bin				            0x1FE000
		esp_init_data_default.bin			    0x1FC000
		boot_v1.5.bin					    0x00000
		user1.2048.new.5.bin			            0x01000
		
		Flash download tool settings:
		CrystalFreq: 26M
		SPI SPEED: 40MHz
		SPID MODE: QIO
		FLASH SIZE: 16Mbit-C11
		
##FOR VERIFY: 
UART0 print as below after boot up.Make sure that the Connect_AP part is successfulESP_8266 will print the local server IP on the UART_0 , mark down this IP address. Open any UDP Tool, configure the UDP to connect to port 1024 and IP from the previous part.use the UDP Tool to Send any strings to ESP_8266. The UDP  client test is successful if the UART can print :

	------------------UDP_RECV_CB---------------
	[Dbg]UDP_RECV_CB len:%d ip:0.0.0.0 port:0
	