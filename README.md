# W5500Interface-STM32Cube

A STM32 HAL library can handle W5500 Wiznet ethernet controller written in C++.

Forked from mbed [W5500Interface](https://os.mbed.com/teams/EthernetInterfaceW5500-makers/code/W5500Interface/).

## API

### Constructor

```cpp
EthernetInterface(SPI_HandleTypeDef* hspi, GPIO_TypeDef* cs_port, uint32_t cs_pin, GPIO_TypeDef* reset_port, uint32_t reset_pin);
```
where,

`SPI_HandleTypeDef* hspi`: Target SPI peripheral HandleTypeDef pointer.

`GPIO_TypeDef* cs_port`: Target GPIO port start address which MFRC522 SPI chip select pin has connected to.

`uint32_t cs_pin`: Target GPIO pin address offset which MFRC522 SPI chip select pin has connected to.

`GPIO_TypeDef* reset_port`: Target GPIO port start address which MFRC522 reset pin has connected to.

`uint32_t reset_pin`: Target GPIO pin address offset which MFRC522 reset pin has connected to.

#### Usage
If W5500 SPI bus is connected to SPI1, chip select pin connected to PA8, and reset pin connected to PB7,
```cpp
EthernetInterface(&hspi1, GPIOA, GPIO_PIN_8, GPIOB, GPIO_PIN_7);
```
If chip select pin and reset pin are user labled as `W5500_CS` and `W5500_RST` on STM32CubeMX and auto-generated by,
```cpp
EthernetInterface(&hspi1, W5500_CS_GPIO_Port, W5500_CS_Pin, W5500_RST_GPIO_Port, W5500_RST_Pin);
```

### Other APIs
All APIs except constructor is identical to mbed library. Check out [mbed W5500Interface API](https://os.mbed.com/teams/EthernetInterfaceW5500-makers/code/W5500Interface/docs/tip/) page.