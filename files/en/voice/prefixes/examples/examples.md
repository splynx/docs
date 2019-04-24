#### Special symbols:

| Symbol      | Description                                                                       |
|-------------|-----------------------------------------------------------------------------------|
| `{x}`       | One digit from 0 to 9.                                                            |
| `{z}`       | One digit from 1 to 9.                                                            |
| `{n}`       | One digit from 2 to 9.                                                            |
| `{!}`       | Zero or more any characters.                                                      |
| `{.}`       | One or more any characters.                                                       |
| `{100-300}` | Number between 100 and 300. You can use any numbers instead of 100 and 300.       |
| `{123|456}` | One of "123" or "456". You can use any string pattern instead of "123" and "456". |

---

#### Examples:

| Phone pattern        | Description                                                                             |
|----------------------|-----------------------------------------------------------------------------------------|
| `+28050420{30-40}`   | Phone must begin with "+28050420" and end with number from 30 to 40.                    |
| `{380|250}{x}{x}{x}` | Phone must begin with one of "380" or "250". Then must be three digit from 0 to 9       |
| `{z}{3|4}{n}{n}`     | Phone must begin with digit from 1 to 9. Then "3" or "4" and then two digit from 2 to 9 |
| `{!}`                | Any phone number                                                                        |


