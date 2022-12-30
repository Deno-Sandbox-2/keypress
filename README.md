### Deno keypress reader

Reads key from stdin.

### Try

```deno run --unstable https://deno.land/x/keypress2@0.1.0/readKeypress_test.ts```

```ts
// CTRL + C keypress
const keypress: Keypress = {
  key: "c",
  code: undefined,
  keyCode: 3,
  sequence: "",
  unicode: "\u0003",
  ctrlKey: true,
  metaKey: false,
  shiftKey: false
}
```

### Usage

Read from Deno.stdin by default:

```ts
import { readKeypress } from "https://deno.land/x/keypress2@0.1.0/mod.ts";

for await (const keypress of readKeypress()) {
    console.log(keypress);

    if (keypress.ctrlKey && keypress.key === 'c') {
        Deno.exit(0);
    }
}
```


Big thanks to Nathan Rajlich and his https://github.com/TooTallNate/keypress, whitch code for key decode I took to this library.
