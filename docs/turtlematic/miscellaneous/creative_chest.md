# Creative chest

Why the hell in creative mode turtle can't generate items? Tell no more, this upgrade just for you.

| Function                                                | Returns | Description                                                          |
|---------------------------------------------------------|---------|----------------------------------------------------------------------|
| generate(item: string, count: number, nbtData: string?) | Result  | Tries to put required item with required count into turtle inventory |

??? "How in hell does nbtData works?"

    NBT data passing from ComputerCraft to Minecraft are ... complicated task. So currently, `nbtData` are just string that expected to be minecraft NBT data serialized into json. 

    You can try `generate("minecraft:potion", 1, "{Potion:\"minecraft:long_regeneration\"}")` to understand how it works
