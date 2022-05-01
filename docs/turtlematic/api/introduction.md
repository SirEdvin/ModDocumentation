# Turtlematic APIs

This section of documentation will describe everything about APIs, that can be provided by different peripherals and general information how to read function tables.

Take a note, that some turtle upgrades (actually, a lot of them) will have extra functions besides supported APIs.

## Parameters description

Functions defined like `call_name(required_arg_1: arg_type_1, required_arg_2: arg_type_2, optional_arg: arg_type_3)`. Some types will have additional limitations, like "only positive numbers", or "only numbers in specific range". In case when limitations are not met, function will throw exception.

## New data types

Mostly this sections contains enums, that are need to be passed as strings. Enums are case-insensetive, so you can pass them as you want.

| Name                | Lua type         | Limitations                           |
|---------------------|------------------|---------------------------------------|
| interactionMode     | string           | Enum with values: any, block, entity  |
| areaInteractionMode | string           | Enum with values: item, block, entity |
| direction           | string           | Enum with values: up, down            |
| Result              | boolean, string? | -

### Interaction mode

All functions, that accept _interactionMode_ as arguments, work with objects in line of sight. They will take as target the first object, that they found. You can force this functions to work only with blocks, or only with entities.

!!! info
    You can get available _interactionMode_ for specific APIs on core documentation page

!!! warning
    Pretty important to note that a lot of entity interaction will be limited to specific entities. For example, Husbandry Automata Core allows to works only with animals. Always checks core documentation page to understand its limitation with entities.

### Area interaction mode

All functions, that accept _areaInteractionMode_ as arguments, work with objects in specific radius around it. You can get this radius via `getConfiguration()` method. Use this parameter to select what objects should to used for operation.

!!! info
    You can get available _areaInteractionMode_ for specific APIs on core documentation page

!!! warning
    Pretty important to note that a lot of entity interaction will be limited to specific entities. For example, Husbandry Automata Core allows to works only with animals. Always checks core documentation page to understand its limitation with entities.

### Direction

All functions, that accept _direction_ as arguments, work with objects in line of sight. You can use this argument to change lint of sight and turtle will begin to start to look down (or up).

### Result

_Result_ are always representing result of called operation. First argument will tell you is operation was successful and second one will tell you reason why operation is failed.

_Result_ can also be parametrized, for example as `Result[number]`, which means it will return operation result as first argument (or nil) and as second argument it will tell you reason why operation is failed.
