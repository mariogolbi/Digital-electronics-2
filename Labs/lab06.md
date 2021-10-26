   | **Function name** | **Function parameters** | **Description** | **Example** |
   | :-- | :-- | :-- | :-- |
   | `lcd_init` | `LCD_DISP_OFF`<br>`LCD_DISP_ON`<br>`LCD_DISP_ON_CURSOR`<br>`LCD_DISP_ON_CURSOR_BLINK` | Display off&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>&nbsp;<br>&nbsp;<br>&nbsp; | `lcd_init(LCD_DISP_OFF);`<br>&nbsp;<br>&nbsp;<br>&nbsp; |
   | `lcd_clrscr` |void |clear display and set cursor to home position | `lcd_clrscr();` |
   | `lcd_gotoxy` | `x`<br>`y`| `horizontal position`<br>`vertical position`<br>`set cursos to specified position`|`lcd_gotoxy(x,y)` |
   | `lcd_putc` |`c` | `character to be displayed`<br>`display character at current position`|`lcd_putc(c)` |
   | `lcd_puts` |`s` | `string to be displayed`<br>display string| `lcd_puts(s)`|
   | `lcd_command` |`cmd` |`intruction to send to controller`<br>`secnd LCd controller instruction command` | |
   | `lcd_data` |`data` |`data byte sent to LCd controller`<br>`send data byte to LCd controller` | |
