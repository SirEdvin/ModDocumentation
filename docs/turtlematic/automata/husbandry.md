# Husbandry automata

!!! picture inline end
    ![Header](./../../images/husbandry_automata_turtle.png){ align=right }

Advanced automata that can harness power of the nature. This automata provider extra capabilities of take care about peaceful mobs and crops (nether wart and cocoa beans included!).

## Obtaining

Feed 1 pig, 1 chiken, 1 sheep and 1 cow souls to [automata core](./automata.md) with [soul scrapper](../miscellaneous/soul_scrapper.md) to obtain it.

## Supported APIs

- [Configuration API](../api/configuration.md)
- [Fuel API](../api/fuel.md)
- [Operation API](../api/operation.md)
- [Look API](../api/look.md)
- [Interaction API](../api/interaction.md): allows interaction with blocks and some entities
- [Scan API](../api/scan.md): allows interaction with items and some entities
- [Capture API](../api/capture.md): only interaction with some entities

## Extra methods

| Function                                          | Returns | Description                                                                                                     |
|---------------------------------------------------|---------|-----------------------------------------------------------------------------------------------------------------|
| harvest(direction?: [Direction](../api/introduction.md#direction))                                            | [Result](../api/introduction.md#result)  | Tries to harvest crop. Crop will not be broken, works like right click harvest      |

## Notes

??? "Which entity are usable for husbandry automata"

    If at least one of criteria met:

    - Entity is friendly
    - Entity have "creature" category
    - Entity have `turtlematic:husbandry_extra_animal` tag

??? "What is count as crops"

    If at least one of criteria met:

    - Block are extends CropBlock
    - Block has age attribute and `turtlematic:husbandry_extra_crops`

??? "Extra information about animals"

    Sometimes[^1] this automata will show extra information about animals when you use [Look](../api/look.md) or [Scan](../api/scan.md) APIs. For example, this is output for sheep

    ```javascript
    {
        "type": "Sheep",
        "name": "Sheep",
        "category": "CREATURE",
        "id": 1269,
        "tags": {},
        "uuid": "0737fd25-a1b6-4a1a-9cdd-3081e0155bb6",
        //here goes extra fields
        "aggresive": false,
        "baby": false,
        "inLove": false,
        "aggresive": false,
        "shearable": true
    }
    ```

??? "Extra information about blocks"

    If block has age property, extra data about it will be provided when you use [Look API](../api/look.md).

    ```javascript
    {
        "age": 2,
        "maxAge": 2,
        "name": "Cocoa",
        "tags": [
            "minecraft:mineable/axe",
            "turtlematic:husbandry_extra_crops"
        ]
    }
    ```

    For beehive and bee nest there a lot of extra data will be provided when you use [Look API](../api/look.md).

    ```javascript
    {
        "honetLevel": 3,
        "name": "Bee Nest",
        "isFull": false,
        "isSmoked": false,
        "bees": [
            {
                "hasFlower": true,
                "hasNectar": true,
                "hasStung": false,
                "health": 10,
                "id": "minecraft:bee",
                "name": "Bee",
                "minOccupationTicks": 2400,
                "ticksInHive": 283
            }
        ]
        "tags": [
            "minecraft:mineable/axe",
            "minecraft:beehives"
        ]
    }
    ```

[^1]: When entity class extends Animal. `shearable` available when entity class extends Animal and implements Shearable interface
