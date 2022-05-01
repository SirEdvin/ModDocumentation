# Mason automata

Automata that harness power of mason villager, allows you to modify appearance of different blocks in world and inventory.

## Obtaining

Feed mason villager to forged automata core with [soul scrapper](../miscellaneous/soul_scrapper.md) to obtain it.

## Supported APIs

- [Configuration API](../api/configuration.md)
- [Fuel API](../api/fuel.md)
- [Operation API](../api/operation.md)
- [Look API](../api/look.md)
- [Experience API](../api/experience.md)

## Extra methods

| Function                                              | Returns | Description                                                                                                                                                                              |
|-------------------------------------------------------|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| getAlternatives("inventory")                          | table   | Returns list of possible alternatives for item in selected slot                                                                                                                          |
| getAlternatives("block", direction?: [Direction](../api/introduction.md#direction))        | table   | Returns list of possible alternatives for block in world                                                                                                                                 |
| chisel("inventory", target: string, limit?: number)    | [Result](../api/introduction.md#result) | Tries to chisel item in selected slot in inventory up to limit amount. Result will be put into inventory, extra items will be dropped in world                                           |
| chisel("block", target: string, direction?: [Direction](../api/introduction.md#direction)) | [Result](../api/introduction.md#result)  | Tries to chisel block in world. If this is possible, block will be transformed in-place, if this is not possible result will be put into inventory, extra items will be dropped in world |
| rotate(rotation: Rotation, direction?: [Direction](../api/introduction.md#direction))      | [Result](../api/introduction.md#result)  | Tries to rotate block in-place                                                                                                                                                           |
| turnOver(direction?: [Direction](../api/introduction.md#direction))                        | [Result](../api/introduction.md#result)  | Tries to turn over block in-place                                                                                                                                                        |
| getPossibleShapes(direction?: [Direction](../api/introduction.md#direction))               | table   | Returns list of possible shapes for block                                                                                                                                                |
| changeShape(shape: string, direction?: [Direction](../api/introduction.md#direction))      | [Result](../api/introduction.md#result)  | Tries to transform block to passed shape

## Notes

??? "Extra information about blocks"

    To help you understand position of block, mason automata will return extra information when using [Look API](../api/look.md)

    ```javascript
    {
        "name": "Mossy Stone Brick Stairs",
        "tags": [
            "minecraft:stairs",
            "minecraft:mineable/pickaxe"
        ],
        "properties": {
            "facing": "north",
            "half": "bottom",
            "shape": "straight",
            "watterlogged": "false"
        }
    }
    ```
