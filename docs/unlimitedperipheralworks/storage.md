# Generic Storage API

Generic storage API are answer for fabric transfer API for items. This API are basically copy of [fluid_storage](https://tweaked.cc/generic_peripheral/fluid_storage.html) API.

??? "Why just don't reuse normal inventory API?"

    Main problem here is that fabric transfer API don't allow to operate any `slots`, just pushing and pulling specific items. So, there is no possible to normally simulite `inventory` API with a large amount of dirty hacks and pain

## Peripheral methods

| Function                                              | Returns | Description                                                                                                                                   |
|-------------------------------------------------------|---------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| items()                                               | table   | Returns items list with description                                                                                                           |
| pushItem(to: string, item?: string, limit?: number    | number  | Tries to push items to target storage. Items, that will be pushed can be limited via `item` parameter and limited via `limit` parameter       |
| pullItem(from: string, item?: string, limit?: number) | number  | Tries to pull items from target storage. Items, that will be pulled can be limited via  `item`  parameter and limited via  `limit`  parameter |
