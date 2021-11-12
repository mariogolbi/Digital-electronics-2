| **Function name** | **Function parameters** | **Description** | **Example** |
   | :-- | :-- | :-- | :-- |
   | `twi_init` | None | Initialize TWI, enable internal pull-up resistors, and set SCL frequency | `twi_init();` |
   | `twi_start` | uint8_t slave_addres | Start communication on TWI bus and send address of TWI slave. <br>&nbsp; | `twi_start((addr<<1)+TWI_READ);` |
   | `twi_write` |uint8_t data  | Send one data byte to TWI slave device <br>&nbsp; |  |
   | `twi_read_ack` | none | Read one byte from TWI slave device and acknowledge it by ACK. <br>&nbsp; | twi_read_nack()  |
   | `twi_read_nack` | none | Read one byte from TWI slave device and acknowledge it by NACK. <br>&nbsp;| twi_read_nack() |
   | `twi_stop` | none | Generates stop condition on TWI bus. | `twi_stop();` |
