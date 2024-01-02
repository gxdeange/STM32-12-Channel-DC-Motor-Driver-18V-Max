# STM32 Based 12-Channel Brushed DC Motor Driver Board @10V Max

STM32F401RCT6 based Stepper Motor Driver capable of running at 10V MAX.

This board is designed for experimental or low current robotics with a max current drive of ~800mA.

Features include:

Reverse Polarity Protection (with LED indicator)

10 X GPIO solder pads (can use standard 2.54mm Dupont Header pins)

USB Mini Connector

Small Form Factor (Approx 36mm X 64mm)

<img width="392" alt="STM32F401RCT6 12-CHANNEL BRUSHED DC MOTOR DRIVER BOARD @10V MAX" src="https://github.com/gxdeange/STM32-12-Channel-Brushed-DC-Motor-Driver-10V-Max/assets/57690555/1fad41d9-36f8-4809-ae4a-735f471248e5">

# Motor Driver / MCU Pin Mappings

M1+ : PB3         M7+ : PC6
M1- : PB4         M7- : PC7

M2+ : PC11        M8+ : PB14
M2- : PC12        M8- : PB15

M3+ : PA12        M9+ : PB12
M3- : PC10        M9- : PB13

M4+ : PA10        M10+ : PB2
M4- : PA11        M10- : PB10

M5+ : PA8         M11+ : PB0
M5- : PA9         M11- : PB1

M6+ : PC8         M12+ : PC4
M6- : PC9         M12- : PC5

![STM32 12-CHANNEL MOTOR : MCU PIN MAPPING](https://github.com/gxdeange/STM32-12-Channel-Brushed-DC-Motor-Driver-10V-Max/assets/57690555/9559372b-2946-4ea1-9e84-6d814d84ad75)

# PROGRAMMING NOTE

This MCU does not use an external crystal and any code must include the following (at the start of your sketch) to ensure the Internal RC clock is used instead. I have created in STM32CubeIDE and set to the max frequency.

void SystemClock_Config(void) {
  RCC_OscInitTypeDef RCC_OscInitStruct = {0};
  RCC_ClkInitTypeDef RCC_ClkInitStruct = {0};

  /** Configure the main internal regulator output voltage
  */
  __HAL_RCC_PWR_CLK_ENABLE();
  __HAL_PWR_VOLTAGESCALING_CONFIG(PWR_REGULATOR_VOLTAGE_SCALE2);

  /** Initializes the RCC Oscillators according to the specified parameters
  * in the RCC_OscInitTypeDef structure.
  */
  RCC_OscInitStruct.OscillatorType = RCC_OSCILLATORTYPE_HSI;
  RCC_OscInitStruct.HSIState = RCC_HSI_ON;
  RCC_OscInitStruct.HSICalibrationValue = RCC_HSICALIBRATION_DEFAULT;
  RCC_OscInitStruct.PLL.PLLState = RCC_PLL_ON;
  RCC_OscInitStruct.PLL.PLLSource = RCC_PLLSOURCE_HSI;
  RCC_OscInitStruct.PLL.PLLM = 8;
  RCC_OscInitStruct.PLL.PLLN = 84;
  RCC_OscInitStruct.PLL.PLLP = RCC_PLLP_DIV2;
  RCC_OscInitStruct.PLL.PLLQ = 4;
  if (HAL_RCC_OscConfig(&RCC_OscInitStruct) != HAL_OK)
  {
    Error_Handler();
  }

  /** Initializes the CPU, AHB and APB buses clocks
  */
  RCC_ClkInitStruct.ClockType = RCC_CLOCKTYPE_HCLK|RCC_CLOCKTYPE_SYSCLK
                              |RCC_CLOCKTYPE_PCLK1|RCC_CLOCKTYPE_PCLK2;
  RCC_ClkInitStruct.SYSCLKSource = RCC_SYSCLKSOURCE_PLLCLK;
  RCC_ClkInitStruct.AHBCLKDivider = RCC_SYSCLK_DIV1;
  RCC_ClkInitStruct.APB1CLKDivider = RCC_HCLK_DIV2;
  RCC_ClkInitStruct.APB2CLKDivider = RCC_HCLK_DIV1;

  if (HAL_RCC_ClockConfig(&RCC_ClkInitStruct, FLASH_LATENCY_2) != HAL_OK)
  {
    Error_Handler();
  }
}
