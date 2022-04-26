# Fuel API

Most of the usage for fuel API comes when you're trying to degrease cooldown for specific operations. If you increase fuel consumption rate for peripheral, automatically it will decrease cooldowns after peripheral method usage (but not initial cooldowns). For example, if click operation required 1 fuel point to perform and will have 5 seconds cooldown, with fuel consumption 2 you can perform click operation one in 2.5 seconds, but in cost of 2 fuel point.

Take a note that fuel point will grow faster, than cooldown drops. Basically, `consumedFuel = 2^(fuelConsumtionRate - 1)`. So fuelConsumtionRate 3 will require 4 fuel points, and fuelConsumtionRate 4 will require 8 fuel points, etc.

!!! warning

    `fuelConsumptionRate` should be positive integer

| Function                             | Returns | Description                                                                                                                    |
|--------------------------------------|---------|--------------------------------------------------------------------------------------------------------------------------------|
| getFuelLevel()                       | number  | Returns current fuel level, for turtle is equivalent for `turtle.getFuelLevel()`                                               |
| getFuelMaxLevel()                    | number  | Returns max fuel level, for turtle is equivalent for `turtle.getFuelLimit()`                                                   |
| getFuelConsumptionRate()             | number  | Return current fuel consumption rate                                                                                           |
| setFuelConsumptionRate(rate: number) | nil     | Tries to set fuel consumption rate to new value. Will throw error if rate lower than 1 or bigger than **maxFuelConsumptionRate** |
