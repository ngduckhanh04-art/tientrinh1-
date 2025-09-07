#include "stm32f10x.h"
#include "stm32f10x_gpio.h"
#include "delay.h"

#define LED_PIN_1  GPIO_Pin_0
#define LED_PIN_2 GPIO_Pin_4

void GPIO_Configure_LED(void) {
    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOA , ENABLE);
    GPIO_InitTypeDef gpio;
    gpio.GPIO_Pin = LED_PIN_1 | LED_PIN_2;
    gpio.GPIO_Speed = GPIO_Speed_50MHz;
    gpio.GPIO_Mode = GPIO_Mode_Out_PP;  
    GPIO_Init(GPIOA, &gpio);
}


int main(void) {
    GPIO_Configure_LED();
		GPIO_ResetBits(GPIOA,LED_PIN_1 | LED_PIN_2);
    while (1) {
       GPIO_SetBits(GPIOA, LED_PIN_1 | LED_PIN_2);
			delay_ms(500);
			GPIO_ResetBits(GPIOA,LED_PIN_1 | LED_PIN_2);
			delay_ms(500);
    }
}
