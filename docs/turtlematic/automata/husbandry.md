# Husbandry automata

Advanced automata that can harness power of the nature.

!!! picture inline end
    ![Header](./../../images/husbandry_automata_turtle.png){ align=right }

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
