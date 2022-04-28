# Soul scrapper

!!! picture inline end
    ![Header](./../../images/soul_scrapper.png){ align=right }

Terrible tool, that allows you to infuse an item in a selected slot with soul of any mob, that you will find on the way.

<br/><br/><br/><br/><br/><br/><br/><br/>

!!! info "What I can infuse?"
    Currently, only [automata core](./../automata/automata.md) can be infused

| Function           | Returns | Description                                                                        |
|--------------------|---------|------------------------------------------------------------------------------------|
| harvestSoul()      | [Result](../api/introduction.md#result)  | Tries to harvest entity soul at line of sight of turtle into item in selected slot |
| getLeftEntities()  | table or nil, string or nil | Tries to get information about left entities to fill soul. Returns table if item in selected slot have started consuming soul and nil with error otherwise

??? "getLeftEntities output examples"

    ```json
    [
        {"name": "Cow", "leftCount": 1},
        {"name": "Sheep", "leftCount": 1},
        {"name": "Pig", "leftCount": 1}
    ]
    ```
