# stm32-
记录常用的技巧

printf打印函数，使能串口，并使能microlib的库

	int fputc(int ch, FILE *f)
	{

		unsigned char temp[1] = {ch};
 
		HAL_UART_Transmit(&huart1,temp,1,10);
 
		return ch;
	}

调试模式 

	#define DUBUG
 
	#ifdef DUBUG
				 #define user_printf(format,...)  printf( format "\r\n", ##__VA_ARGS__) 
				 #define user_info_printf(format,...)  printf( "{main info:}" format "\r\n", ##__VA_ARGS__) 
				 #define user_error_printf(format,...)  printf( "{main error:}"format "\r\n", ##__VA_ARGS__) 
		#else 
		     #define user_printf(format,...)
	#endif
