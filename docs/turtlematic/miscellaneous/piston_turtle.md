# Piston and sticky piston turtles

!!! picture inline end
    ![Header](./../../images/piston_turtle.png){ align=right }

So, this is piston turtle! Now piston and sticky piston are valid upgrades for turtles and can be attached to them!

<br/><br/><br/><br/><br/>

## Piston methods

| Function           | Returns | Description                                                                        |
|--------------------|---------|------------------------------------------------------------------------------------|
| push(direction?: [Direction](../api/introduction.md#direction))      | [Result](../api/introduction.md#result)  | Tries to push block that currently facing. Works exacly like piston |

## Sticky piston methods

| Function           | Returns | Description                                                                        |
|--------------------|---------|------------------------------------------------------------------------------------|
| push(direction?: [Direction](../api/introduction.md#direction))      | [Result](../api/introduction.md#result)  | Tries to push block that currently facing. Works exactly like piston |
| pull(direction?: [Direction](../api/introduction.md#direction))      | [Result](../api/introduction.md#result)  | Tries to pull block that currently facing. Between this block and turtle should be one empty block. Works exactly like sticky piston collapsing |
