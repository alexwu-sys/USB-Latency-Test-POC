# USB Latency Measurement POC
**This is a common repository for POC and developed by CPS/Security & Manageability team**

  Manager:   Yiying, Shao - yiying.shao@intel.com)
  
  Contribuor : Zhidong (Edward), Duan - zhidong.duan@intel.com);
               : Alex, Wu - alex.wu@intel.com

# Hardward and Software
> **Teensy 4.1**

> **Visual Studio 2019 with MFC package**

# Results for reference
![alt text](https://github.com/alexwu-sys/USB_Latency_POC/blob/main/Pictures/board.jpg)
![alt text](https://github.com/alexwu-sys/USB_Latency_POC/blob/main/Pictures/Connections.png)
![alt text](https://github.com/alexwu-sys/USB_Latency_POC/blob/main/Pictures/TeensyPins.jpg)
![alt text](https://github.com/alexwu-sys/USB_Latency_POC/blob/main/Pictures/LCD_Pins.png)

# Protocol format
| Byte | 0    | 1    | 2    | 3 ~ 6|
| :---:   | :---: | :---: | :---: | :---: | 
| Bitwise | 7~0   | 7~0   | 7~0   | 0x12345678(31~0) => 0x78563412|
| Symbol | S/E   | Count   |  X/T  | Microsecond(32 bits) |

typedef struct {

    uint8_t startEnd;
    
    uint8_t Symbol; /* X: X86 Host T: Device Teensy */
    
    uint16_t count; //Max count is 1~255
    
    uint32_t Microsecond;
    
    uint8_t Reserved[56];
    
} USBPingMessage; //Total 64 bytes


# Useful links
|Title |Link|
|:-----:|---------------|
|Teensy 4.1 board|https://www.pjrc.com/store/teensy41.html|
|IlI9341 For T4|https://github.com/vindar/ILI9341_T4|
| FAQ    |
