# STM32G431RB TIM1 and TIM8 synchronization example
Timer synchronization for STM32G431 like TIM1 as a master timer and TIM8 as a slave timer.

# TIM1 Configuration(Master)
- TRGO : CNT_EN means MMS[3:0]: Master mode selection : 0001: Enable - the Counter Enable signal CNT_EN is used as trigger output (tim_trgo)
- Master/Slave Mode(MSM bit) : enable means Master/slave mode : 1: The effect of an event on the trigger input (tim_trgi) is delayed to allow a perfect
synchronization between the current timer and its slaves (through tim_trgo). It is useful if we want to synchronize several timers on a single external event.

# TIM8 Configuration(Slave)
- Slave Mode : Tigger Mode means SMS[3:0]: Slave mode selection : 0110: Trigger Mode - The counter starts at a rising edge of the trigger tim_trgi (but it is not reset). Only the start of the counter is controlled.
- Tigger Source : ITR0 means TS[2:0]: Trigger selection : 00000: Internal Trigger 0 (tim_itr0 - tim1_trgo)

