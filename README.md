# eLooM_t
Template projects for an eLooM framework based application.

The purpose of the template project is to provide a starting project, based on eLooM, for a given STM32 family. So it has only one managed task (HelloWorldTask) that extend the AManagedTask base class. The task control loop is a periodic loop with 1s period, and, at each iteration, it displays the message “Hello World” in the Debug log. The Debug log normally uses the VCom port of the STLINK, and it is possible to view the log in the host PC through an hyper terminal application connected to the board with the following parameters:
- Baud rate: 115200
- Word length: 8 bit
- Stop bits: 1
- Parity: none
- Flow control: none

The exact value of the parameters parameters can be checked in the file Application/mx/usart.c.

HelloWorldTask can also use an object from the Low Level API layer to dimostrate the interaction between the different layers in a eLooM based application. For this purpose the template application come with a driver, a PushButtonDrv. It is instantiated by the HelloWorldTask instance and it configures one user button in the development board as external interrupt.

Every time the button is pressed, the HelloWorldTask generates a PM transaction between STATE1 and TEST states.


## Folder organization
This repository contains template projects for different STM32 family. Each project has been developed on a specific board, but it
is easy to port to a different board of the same MCU family.

The folder organization ties to be inline with STMicroelectronics guidelines. For more information see section  _4.3 Packaging model_  of [UM2388 - Development guidelines for STM32Cube firmware Packs](https://www.st.com/resource/en/user_manual/um2388-development-guidelines-for-stm32cube-firmware-packs-stmicroelectronics.pdf 'UM2388')


## Available projects template

 - STM32L4R9ZI-STWIN
 - STM32L562E-DK