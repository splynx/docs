#### Special symbols supported:

| Symbol      | Description                                                                       |
|-------------|-----------------------------------------------------------------------------------|
| `{!}`       | Zero or more any characters.                                                      |

---

#### Examples:

| Phone pattern        | Description                                                                             |
|----------------------|-----------------------------------------------------------------------------------------|
| `{!}`                | Any phone number                                                                        |
| `260{!}`            | Any phone number started from 260                                                       |

**Important**

The previous complex patters, like `{x}` (one digit from 0 to 9), `{.}` (one or more any characters), `{n}` (one digit from 2 to 9) etc. are no longer supported in Splynx.

In case complex patters have already been used, it is necessary to change them.
