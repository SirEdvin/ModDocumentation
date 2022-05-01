# Husbandry automata

!!! picture inline end
    ![Header](./../../images/husbandry_automata_turtle.png){ align=right }

Advanced automata that can harness power of the nature.

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

## Notes

??? "Which entity are usable for husbandry automata"

    If at least one of criteria met:

    - Entity is friendly
    - Entity have "creature" category
    - Entity have `turtlematic:husbandry_extra_animal` tag

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

[^1]: When entity class extends Animal. `shearable` available when entity class extends Animal and implements Shearable interface
