# stm32-
记录常用的技巧

printf打印函数，使能串口，并使能microlib的库

int fputc(int ch, FILE *f)
{

	unsigned char temp[1] = {ch};
 
	HAL_UART_Transmit(&huart1,temp,1,10);
 
	return ch;
}

