# Look API

Look API are mostly just improved `inspect` from ComputerCraft Turtle API. It is not pretty useful by itself, but it helps to understand who will be targeted of another APIs, like [Interaction API](interaction.md) or [Capture API](capture.md).

| Function                                           | Returns | Description                                                                                                                                                                                                                          |
|----------------------------------------------------|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| look(mode: [InteractionMode](./introduction.md#interaction-mode), direction?: [Direction](./introduction.md#direction)) | table   | Returns detailed information about first target in line of sight.  |

??? "Look output examples"

    === "Entity"

        ```json
        {
            "type": "Cow",
            "name": "Cow",
            "category": "CREATURE",
            "id": 1269,
            "tags": {},
            "uuid": "0737fd25-a1b6-4a1a-9cdd-3081e0155bb6"
        }
        ```

    === "Block"

        ```json
        {
            "name": "Grass Block",
            "tags": [
                "minecraft:valid_spawn",
                "minecraft:lush_ground_replaceable",
                "minecraft:big_dripleaf_placeable",
                "minecraft:animals_spawnable_on",
                "computercraft:turtle_shovel_harvestable",
                "minecraft:moss_replaceable",
                "minecraft:azalea_root_replaceable",
                "minecraft:rabbits_spawnable_on",
                "minecraft:foxes_spawnable_on",
                "minecraft:parrots_spawnable_on",
                "minecraft:dirt",
                "minecraft:enderman_holdable",
                "minecraft:mineable/shovel",
                "minecraft:bamboo_plantable_on",
                "minecraft:azalea_grows_on",
                "minecraft:wolves_spawnable_on"
            ]
        }
        ```
