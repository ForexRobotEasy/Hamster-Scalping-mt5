# Hamster Scalping Expert Advisor

This is the code for the Hamster Scalping Expert Advisor, developed by the Forex Robot Easy Team. Hamster Scalping is a powerful forex software designed for night scalping strategy. This Expert Advisor uses the RSI indicator and Average True Range (ATR) to identify entry conditions for buying and selling.

For detailed reviews and trading results of this product, please visit [Forex Robot Easy - Hamster Scalping Review](https://forexroboteasy.com/forex-robot-review/review-hamster-scalping-mt5-a-powerful-forex-software-for-night-scalping-strategy/). Please note that Forex Robot Easy is not the official developer of this product. We only provide the sample code that can work as described in this product. To find the official developer of this product, please refer to MQL5.

## Input Parameters

- LotSize: Lot size for each trade (default: 0.01)
- StopLoss: Stop loss in pips (default: 50)
- TakeProfit: Take profit in pips (default: 100)
- RSI_Period: RSI period (default: 14)
- RSI_Threshold: RSI threshold for entry (default: 30)
- ATR_Period: ATR period (default: 14)
- ATR_Multiplier: ATR multiplier for entry (default: 2)

## Global Variables

- ticket: Order ticket number
- atrValue: ATR value
- rsiValue: RSI value

## Initialization

The OnInit() function is called during the initialization of the Expert Advisor. It sets certain conditions and parameters required for the EA to function properly.

1. It checks if the account type is hedging. If not, it displays a message and returns INIT_FAILED.
2. It checks if the account balance is at least $100. If not, it displays a message and returns INIT_FAILED.
3. It checks if the account type is ECN. If not, it displays a message and returns INIT_FAILED.
4. It checks if the minimum spread is 0. If not, it displays a message and returns INIT_FAILED.
5. It sets the currency pair to EURUSD and the timeframe to M5.
6. It returns INIT_SUCCEEDED if all conditions are met.

## Expert Advisor Execution

The OnTick() function is called on each tick of the chart. It calculates the ATR value and RSI value using the iATR() and iRSI() functions respectively. It then checks for entry conditions based on the RSI threshold and ATR multiplier.

1. If the RSI value is below the RSI threshold and the ATR value is greater than the ATR multiplier * Point, a buy order is placed.
2. If the RSI value is above (100 - RSI threshold) and the ATR value is greater than the ATR multiplier * Point, a sell order is placed.
3. If the order placement is successful, it prints a message. Otherwise, it prints a failure message.

## Expert Advisor Deinit

The OnDeinit() function is called when the Expert Advisor is removed from the chart. It closes any open orders associated with the EA.

1. It iterates through all open orders using the OrdersTotal() function.
2. It selects each order using OrderSelect() and checks if it belongs to the EA based on the symbol and magic number.
3. If the order belongs to the EA, it closes the order using OrderClose().
4. It uses clrNONE as the color parameter for the OrderClose() function.

Please note that this is a sample code provided by Forex Robot Easy and may require further customization or optimization for specific trading strategies and platforms.
