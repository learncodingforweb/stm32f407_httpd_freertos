(HAL_ETH_Transmit_IT(&heth, &TxConfig) == HAL_OK) {
    while(osSemaphoreAcquire(TxPktSemaphore, TIME_WAITING_FOR_INPUT)!=osOK)

    {
    }

    HAL_ETH_ReleaseTxPacket(&heth);
  } else {
    pbuf_free(p);
  }
it wait indefinitely on 	configASSERT( pxQueue->uxItemSize == 0 );?
Behaviour is unpredictable. do not know when this problem comes.
