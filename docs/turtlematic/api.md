# Turtlematic APIs

## New data types

Mostly this sections contains enums, that are need to be passed as strings. Enums are case-insensetive, so you can pass them as you want.

| Name                | Lua type         | Limitations                           |
|---------------------|------------------|---------------------------------------|
| interactionMode     | string           | Enum with values: any, block, entity  |
| areaInteractionMode | string           | Enum with values: item, block, entity |
| direction           | string           | Enum with values: up, down            |
| Result              | boolean, string? | -

### Interaction mode

All functions, that accept _interactionMode_ as arguments, works with objects in line of sight. They will take as target first object, that they found. You can force this functions to work only with blocks, or only with entities.

!!! info
    You can get awailable _interactionMode_ for specific APIs with `getConfiguration()` method.

!!! warning
    Pretty important to note that a lot of entity interaction will be limited to specific entities. For example, Husbandry Automata Core allows to works only with animals. Always checks core documentation page to understand it's limitation with entities.

### Area interaction mode

All functions, that accept _areaInteractionMode_ as arguments, works with objects in specific radius around it. You can get this radius via `getConfiguration()` method. Use this parameter to select what objects should to used for operation.

!!! info
    You can get awailable _areaInteractionMode_ for specific APIs with `getConfiguration()` method.

!!! warning
    Pretty important to note that a lot of entity interaction will be limited to specific entities. For example, Husbandry Automata Core allows to works only with animals. Always checks core documentation page to understand it's limitation with entities.

### Direction

All functions, that accept _direction_ as arguments, works with objects in line of sight. You can use this argument to change lint of sight and turtle will begin to start look down (or up).

### Result

_Result_ are always represent result of called operation. First argument will tell you is operation was successful and second one will tell you reason why operation are failed.


## Configuration API

Configuration API allows peripheral user to understand current peripheral limitations and how you can use it. Any additional limit, that provided by peripheral can be retrived from `getConfiguration()` method. Values, that can be retrived with help of this method are marked like **valueInConfiguration** in this documentation.

| Function           | Returns | Description                                                                                                                             |
|--------------------|---------|-----------------------------------------------------------------------------------------------------------------------------------------|
| getConfiguration() | table   | Returns table with configuration.  |

## Operation API

Operation API mostly responsible for thoose peripheral methods, that are somehow influence surrounding worlds. Most of this operations will have cooldowns - so you can't call them without delay. Also, some operation with long cooldowns we have it at each turtle start or upgrade equipment, so take this to account.

You can configure cooldowns in configuration file. Also, threshold for initial cooldown also can be configured via `initialCooldownSensetiveLevel` or even disabled with `isInitialCooldownEnabled` settings key.

| Function                           | Returns                 | Description                                    |
|------------------------------------|-------------------------|------------------------------------------------|
| getCooldown(operationName: string) | number                  | Returns times in milliseconds of left cooldown |
| getOperations()                    | table (list of strings) | Returns all awailable operations               |

## Fuel API

Most of usage for fuel API comes when you trying to degrease cooldown for specific operations. If you increase fuel consumption rate for peripheral, automatically it will descrese cooldowns after peripheral method usage (but not initial cooldowns). For example, if click operation required 1 fuel point for perform and will have 5 seconds cooldown, with fuel consumption 2 you can perform click operation one in 2.5 seconds, but in cost of 2 fuel point.

Take a note that fuel point will grow faster, than cooldown drops. Basically, `consumedFuel = 2^(fuelConsumtionRate - 1)`. So fuelConsumtionRate 3 will required 4 fuel points, and fuelConsumtionRate 4 will required 8 fuel points, etc.

| Function                             | Returns | Description                                                                                                                    |
|--------------------------------------|---------|--------------------------------------------------------------------------------------------------------------------------------|
| getFuelLevel()                       | number  | Returns current fuel level, for turtle is equivalent for `turtle.getFuelLevel()`                                               |
| getFuelMaxLevel()                    | number  | Returns max fuel level, for turtle is equivalent for `turtle.getFuelLimit()`                                                   |
| getFuelConsumptionRate()             | number  | Return current fuel consumption rate                                                                                           |
| setFuelConsumptionRate(rate: number) | nil     | Tries to set fuel consumption rate to new value. Will throw error if rate lower then 1 or bigger than **maxFuelConsumptionRate** |

## Look API

Look API are mostly just impoved `inspect` from ComputerCraft Turtle API. It is not pretty useful by itself, but it helps to understand who will be target of another APIs, like Interaction API or Capture API.

| Function                                           | Returns | Description                                                                                                                                                                                                                          |
|----------------------------------------------------|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| look(mode: [InteractionMode](#interaction-mode), direction: [Direction](#direction)?) | table   | Returns detailed information about first target on line of sight.  |

## Interaction API

Interaction API allows to fully simulate players left and right clicks. However, instead of simple simulation this API provides some benefits:

- All loot will be automatically collected
- For some core tiers tool will not be damaged
- Left clicks are always charged. So sword will always hit with full power

| Function                                            | Returns | Description                                    |
|-----------------------------------------------------|---------|------------------------------------------------|
| use(mode: [InteractionMode](#interaction-mode), direction: [Direction](#direction)?)   | [Result](#result)  | Emulates rightClick with item in selected slot |
| swing(mode: [InteractionMode](#interaction-mode), direction: [Direction](#direction)?) | [Result](#result)  | Emulates leftClick with item in selected slot  |

## Capture API

Capture API allows to moving block or entities with storing it internal data! So finally, you can move specific spawners and chests!

Take a note, that released entity or block will be placed at front of turtle. Also, block can be placed only on empty space

| Function                                              | Returns | Description                                                    |
|-------------------------------------------------------|---------|----------------------------------------------------------------|
| capture(mode: [InteractionMode](#interaction-mode), direction: [Direction](#direction)?) | [Result](#result)  | Tries to capture object: entity or block                       |
| release()                                             | [Result](#result)  | Tiers to release object: create entity or place block          |
| getCaptured()                                         | table   | Returns information about captured entity (including NBT data) |

## Scan API

## Warp API
