# Interaction API

Interaction API allows to fully simulate player left and right clicks. However, instead of simple simulation this API provides some benefits:

- All loot will be automatically collected
- For some core tiers tool will not be damaged
- Left clicks are always charged. So sword will always hit with full power

| Function                                            | Returns | Description                                    |
|-----------------------------------------------------|---------|------------------------------------------------|
| use(mode: [InteractionMode](./introduction.md#interaction-mode), direction?: [Direction](./introduction.md#direction))   | [Result](./introduction.md#result)  | Emulates rightClick with item in selected slot |
| swing(mode: [InteractionMode](./introduction.md#interaction-mode), direction?: [Direction](./introduction.md#direction)) | [Result](./introduction.md#result)  | Emulates leftClick with item in selected slot  |
