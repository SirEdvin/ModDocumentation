# Brewing automata

Automata that harness power of cleric villager, allows you to perform brew potions, throw it and curing villagers

## Obtaining

Feed cleric villager to forged automata core with [soul scrapper](../miscellaneous/soul_scrapper.md) to obtain it.

## Supported APIs

- [Configuration API](../api/configuration.md)
- [Fuel API](../api/fuel.md)
- [Operation API](../api/operation.md)
- [Look API](../api/look.md)
- [Experience API](../api/experience.md)
- [Scan API](../api/scan.md): only for items and zombie villagers
- [Interaction API](../api/interaction.md): only for blocks and zombie villagers

## Extra methods

| Function                                          | Returns | Description                                                                                                     |
|---------------------------------------------------|---------|-----------------------------------------------------------------------------------------------------------------|
| brew()                                            | [Result](../api/introduction.md#result)  | Performs brew operations, applying item in selected slot as brewing component to all potions in inventory.      |
| throwPotion(power?: number, uncertainty?: number) | [Result](../api/introduction.md#result)  | Throws potion in selected slot with provided power (controls max distance) and uncertainty (controls deviation) |

## Notes

??? "XP notes"

    Brewing operations often provides some XP that will be stored in turtle

??? "Extra information about zombie villagers"

    To help you understand power of your potions, you will receive extra information about entities with [Look API](../api/look.md) and [Scan API](../api/scan.md)

    ```javascript
    {
        "type": "Cow",
        "name": "Cow",
        "category": "CREATURE",
        "id": 1269,
        "tags": {},
        "uuid": "0737fd25-a1b6-4a1a-9cdd-3081e0155bb6",
        "effects": [
            {
                "amplifier": 0,
                "duration": 1474,
                "isAmbient": false,
                "name": "Regeneration",
                "technicalName": "effects.minecraft.regeneration"
            }
        ]
    }
    ```

??? "How do I supposed to get water bottles?"

    You can `use` glass bottles on water sources
