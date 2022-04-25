# Warp API

Warp API essentially comes from harvesting power of The End itself. It allows you to jump to previously stored points instantly and with reduced cost.

!!! danger

    Due to ComputerCraft limitations all stored points data will be lost if you unequip turtle upgrade.

!!! danger

    This API is dimension-bound. If you somehow change turtle dimension this will require full reset

!!! warning

    Points are limited per upgrade. It controlled by `endAutomataCoreWarpPointLimit` Minecraft settings and by default it is 64

| Function                       | Returns                  | Description                                                    |
| ------------------------------ | ------------------------ | -------------------------------------------------------------- |
| savePoint(name: string)        | [Result](./introduction.md#result)        | Saves current turtle location into data for future use         |
| deletePoint(name: string)      | [Result](./introduction.md#result)        | Delete points if it exists                                     |
| warpToPoint(name: string)      | [Result](./introduction.md#result)        | Teleport turtle to stored point if turtle has enough fuel      |
| points()                       | table                    | Returns list of point names                                    |
| estimateWarpCost(name: string) | number                   | Returns cost of warp in fuel                                   |
| distanceToPoint(name: string   | number                   | Return manhattan distance to point                             |
