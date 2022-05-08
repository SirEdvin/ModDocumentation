# Lectern

!!! picture inline end
    ![Header](./../../images/lectern.png){ align=right }

Some librarian often founds lectern pretty useful, but it was always a problem to write long books. Now you can do it with one little program!

<br/><br/><br/><br/><br/>

## Peripheral methods

| Function                                | Returns | Description                                                                                                                           |
|-----------------------------------------|---------|---------------------------------------------------------------------------------------------------------------------------------------|
| hasBook()                               | boolean | If lectern has book, return true, else false                                                                                          |
| getPageCount()                          | number  | Returns page count, error if no book on lectern                                                                                       |
| getActivePage()                         | number  | Returns active page for book on lectern, error if no book on lectern                                                                  |
| setActivePage(page: number)             | nil     | Tries to set new active page for lectern. Error if no book or page number not between 1 and pageCount                                 |
| getText()                               | table   | Returns a list of strings with text in book                                                                                           |
| isBookEditable()                        | boolean | Returns true if book can be edited via this API                                                                                       |
| addPage(text?: string)                  | boolean | Tries to add new page with text if passed (or empty text). Error if no book or book is not editable                                   |
| removePage(page: number)                | boolean | Tries to remove existed page. Error if no book or book is not editable or page number is not correct                                  |
| editPage(page: number, text: string)    | boolean | Tries to change page text. Error if no book or book is not editable or page number is not correct                                     |
| ejectBook(to: string)                   | [Result](./../../turtlematic/api/introduction.md#result)  | Tries to move book on lectern to target storage                                                                                       |
| injectBook(from: string, name?: string) | [Result](./../../turtlematic/api/introduction.md#result)  | Tries to move book to lectern from target storage. Will transfer first suitable book. If name provided, book will be filtered by name |
