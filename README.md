# STM32F411-I2C-Search
I2C Search code for STM32F411 Nucleo with HAL Library and CubeMX.  

(en)
## How to use 
  * Write bin data in Debug Folder to your Nucleo board (Drag & Drop as same as mbed).
  * Connect i2c devices to Power and D15:SCL, D14:SDA.
  * Open Debug COM port of STLink with Serial terminal software such as a teraterm.  
  * Baud rate of the COM port is 9600bps.  
  * You can search address of I2C devices.
  * Found devices are marked as "[0xXX]". 
  * Then you can make your device code with HAL_I2C_Mem_Read & HAL_I2C_Mem_Write with found addresses. 
  

<img src="https://github.com/meerstern/STM32F411-I2C-Search/blob/master/i2csearch.png" width="360">

Sample of this code.  
In this case, MPU6050 is connected to STM32F411 Nucleo.  
Then the address is 0xD0 and HAL_I2C_Mem_Read(hi2c,0xD0,reg,I2C_MEMADD_SIZE_8BIT,&data,size,100),  
HAL_I2C_Mem_Write(hi2c,0xD0,reg,I2C_MEMADD_SIZE_8BIT,data,size,100).  
 
## Others
 * This code can be easily ported to other stm32 MPU with HAL Library.  
 * Main Function is I2C_Dev_Search().  
 

(ja)
## 使用方法  
  * Debugフォルダ内の*.binファイルをmbedとして認識されたSTM32F411Nucleoボードに書き込んでください。  
  * I2Cデバイスの電源とD15にSCL、D14にSDAを接続してください。  
  * STLinkのシリアルポートをteraterm等のターミナルソフトで開いてください。  
  * ボーレートは9600bpsです。  
  * 数秒毎にI2Cデバイスの検索を行い、デバイス一覧が表示されます。  
 
 
## その他  
  * HALライブラリを使用しているため、他のSTM32マイコンでもコードを移植すれば使用可能です。  
  * 検索で使用する関数はI2C_Dev_Search()です。  
  
 
License - MIT
