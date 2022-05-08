# Note Block

!!! picture inline end
    ![Header](./../../images/noteblock.png){ align=right }

If you even dream about building automatic ensemble, here is your building blocks!

<br/><br/><br/><br/><br/><br/>

## Peripheral methods

| Function                    | Returns | Description                                                             |
|-----------------------------|---------|-------------------------------------------------------------------------|
| getNote()                   | number  | Returns current note                                                    |
| setNote(note: number)       | nil     | Set note to desired, note should be from 0 to 24                        |
| getInstrument()             | string  | Returns current instrument                                              |
| setInstrument(name: string) | nil     | Tries to set new instrument. You can get possible instruments from here |
| play()                      | nil     | Plays note                                                              |
