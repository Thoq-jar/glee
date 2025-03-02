# glee

Glee is a simple way to parse JSON by taking in JSON and
returning a string.

This is my first package, i'm new to gleam- I'm sure there
are things I could do better

[![Package Version](https://img.shields.io/hexpm/v/glee)](https://hex.pm/packages/glee)
[![Hex Docs](https://img.shields.io/badge/hex-docs-ffaff3)](https://hexdocs.pm/glee/)

```sh
gleam add glee@1
```

Getting a string:
```gleam
import glee

pub fn main() {
  let json = "{\"name\":\"John\",\"age\":30}"
  let result = glee.parse_json_string(json, "name")
  io.println("Name: " <> result)
}
```

Getting a float:
```gleam
import glee
import gleam/io
import gleam/float
import gleam/result

pub fn main() {
  let json = "{\"name\":\"John\",\"age\":30.4}"
  let result = glee.parse_json_float(json, "age")
  
  case result {
    Ok(age) -> io.println("Age: " <> float.to_string(age))
    Error(reason) -> io.println("Error: " <> reason)
  }
}
```

Getting an int:
```gleam
import glee
import gleam/io
import gleam/int
import gleam/result

pub fn main() {
  let json = "{\"name\":\"John\",\"age\":30}"
  let result = glee.parse_json_int(json, "age")
  
  case result {
    Ok(age) -> io.println("Age: " <> int.to_string(age))
    Error(reason) -> io.println("Error: " <> reason)
  }
}
```
Further documentation can be found at <https://hexdocs.pm/glee>.

## Development

```sh
gleam test  # Run the tests
```
