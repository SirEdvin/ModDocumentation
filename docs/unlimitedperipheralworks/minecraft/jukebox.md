# Jukebox

!!! picture inline end
    ![Header](./../../images/jukebox.png){ align=right }

Pretty standard jukebox integration, that allows you to make automatic playlist.

<br/><br/><br/><br/><br/>

## Peripheral methods

| Function                               | Returns | Description                                                        |
|----------------------------------------|---------|--------------------------------------------------------------------|
| getDisc()                              | table   | Returns information about stored disc or nil                       |
| replay()                               | nil     | Starts play disc again, error if no disc inside                    |
| stop()                                 | nil     | Stop playing disc                                                  |
| ejectDisc(to: string)                  | [Result](./../../turtlematic/api/introduction.md#result)  | Tries to move disc from jukebox to target inventory                |
| injectDisc(from: string, item: string) | [Result](./../../turtlematic/api/introduction.md#result)  | Tries to move disc with id `item` from target inventory to jukebox |
