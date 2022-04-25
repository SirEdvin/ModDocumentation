# Scan API

!!! Axises inline end
    ![Header](../images/turtle_coordinates.png){ align=right }

    Illustrative description of relative coordinate axes for turtle

Scan API is an interesting one. It allows use to analyze environment around turtle in specific **radius**. However, result always will be orientation-related, direction in which turtle facing will be counted as X axis and direction at right of turtle will be counted as Z axis. This behavior will match Minecraft world axes when turtle facing east.

<br/><br/><br/><br/><br/>

| Function                                         | Returns | Description                                                                                                     |
|--------------------------------------------------|---------|-----------------------------------------------------------------------------------------------------------------|
| scan(mode: [AreaInteractionMode](./introduction.md#area-interaction-mode), radius?: number) | table   | Scan surrounded area for objects with selected mode. Radius is optional, by default it will be max **radius** for core |

??? "Scan output examples"

    === "Items"

        ```json
        [
            {
                "x": -1,
                "y": 0,
                "z": 0,
                "count": 2,
                "maxStackSize": 64,
                "tags": [
                    "minecraft:piglin_loved",
                    "computercraft:turtle"
                ],
                "technicalName": "computercraft:turtle_advanced",
                "name": "Advanced Wireless Automata Turtle"
            },
            {
                "x": 0,
                "y": 0,
                "z": -1,
                "count": 1,
                "maxStackSize": 64,
                "tags": [
                    "minecraft:piglin_loved",
                    "computercraft:computer"
                ],
                "technicalName": "computercraft:computer_advanced",
                "name": "Advanced Computer"
            }
        ]
        ```

    === "Entity"

        ```json
        [
            {
                "type": "Panda",
                "tags": {},
                "id": 19,
                "y": 0,
                "x": -16,
                "name": "Panda",
                "category": "CREATURE",
                "z": -17,
                "uuid": "f5bd1195-9466-4106-ab94-0c9a854b6b5f"
            },
            {
                "type": "Panda",
                "tags": {},
                "id": 39,
                "y": 0,
                "x": 11,
                "name": "Pretty awesome panda",
                "category": "CREATURE",
                "z": -12,
                "uuid": "db90ecf0-57f6-40b2-8c2a-0d959d477937"
            }
        ]
        ```

    === "Block"

        ```json
        [
            {
                "y": -1,
                "x": -1,
                "name": "Polished Granite",
                "z": 1,
                "tags": [
                    "minecraft:mineable/pickaxe"
                ]
            },
            {
                "y": -1,
                "x": 0,
                "name": "Polished Granite",
                "z": 1,
                "tags": [
                    "minecraft:mineable/pickaxe"
                ]
            },
            {
                "y": -1,
                "x": 1,
                "name": "Polished Granite",
                "z": 1,
                "tags": [
                    "minecraft:mineable/pickaxe"
                ]
            },
            {
                "y": -1,
                "x": -1,
                "name": "Polished Granite",
                "z": 0,
                "tags": [
                    "minecraft:mineable/pickaxe"
                ]
            },
            {
                "y": -1,
                "x": 0,
                "name": "Polished Granite",
                "z": 0,
                "tags": [
                    "minecraft:mineable/pickaxe"
                ]
            },
            {
                "y": -1,
                "x": 1,
                "name": "Polished Granite",
                "z": 0,
                "tags": [
                    "minecraft:mineable/pickaxe"
                ]
            },
            {
                "y": 0,
                "x": 0,
                "name": "Advanced Turtle",
                "z": 0,
                "tags": [
                    "computercraft:turtle",
                    "minecraft:mineable/pickaxe"
                ]
            },
            {
                "y": -1,
                "x": -1,
                "name": "Polished Granite",
                "z": -1,
                "tags": [
                    "minecraft:mineable/pickaxe"
                ]
            },
            {
                "y": -1,
                "x": 0,
                "name": "Polished Granite",
                "z": -1,
                "tags": [
                    "minecraft:mineable/pickaxe"
                ]
            },
            {
                "y": -1,
                "x": 1,
                "name": "Polished Granite",
                "z": -1,
                "tags": [
                    "minecraft:mineable/pickaxe"
                ]
            }
        ]
        ```
