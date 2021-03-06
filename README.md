# hdlbr - [Handlebars](https://handlebarsjs.com) CLI

## Usage

````sh
hdlbr VARIABLES_FILE TEMPLATE_FILE
````

Where:
- VARIABLES_FILE is a JSON map, listing all vars.
- TEMPLATE_FILE is a Handlebars template.

## Example

`vars.json`:

````json
{
  "name": "Foo",
  "comments": [
    {
      "author": "Dracula"
    },
    {
      "author": "Alucard"
    }
  ]
}
````

`template.hbs`:

````handlebars
Hello {{name}}
{{~#each comments}}
  {{author}}
{{~/each~}}
````

Result of `hdlbr vars.json template.hbs`:

````
Hello Foo
  Dracula
  Alucard
````

## Build

You may use Rust 2018 and Cargo to build:

````
cargo build --release
````
