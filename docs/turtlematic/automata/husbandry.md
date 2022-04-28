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
- [Interaction API](../api/interaction.md): allows interaction with blocks and animals
- [Scan API](../api/scan.md): allows interaction with items and animals
- [Capture API](../api/capture.md): only interaction with animals

??? "How automata will detect that entity is animal?"

    If at least one of criteria met:

    - Entity is friendly
    - Entity have "creature" category
    - Entity have `turtlematic:husbandry_extra_animal` tag
