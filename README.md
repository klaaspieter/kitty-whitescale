# Kitty whitescale

A whitescale colorscheme meant to keep its colors in white, black, and gray.

[Screenshot](https://p80.f1.n0.cdn.getcloudapp.com/items/7KuyBYyy/Image+2019-12-03+at+12.27.33+PM.png?v=97128bde07584aafb435ae8d206f5036)

## Installation

Open the directory with your Kitty config:

```sh
cd ~/.config/kitty
```

Clone the repo:

```sh
https://github.com/klaaspieter/kitty-whitescale.git
```

Symlink the whitescale config:

```sh
ln -s ./whitescale/whitescale.conf ~/.config/kitty/theme.conf
```

Add this line to your kitty.conf configuration file:

```sh
include ./theme.conf
```

## Building from source

Print the config to the console:

```sh
./bin/generate
```

Or write it to a file:

```sh
./bin/generate > test.theme
```

The script in `./bin/generate` automatically generates the kitty config. It does so by taking [this list of 256 (Xterm) colors][256 colors] ([json][256 colors json]). It applies the [luminosity method] to each color which results in a set of grayscale colors.

The luminosity method:

```
Luminosity = 0.21 × Red + 0.72 × Green + 0.07 × Blue
```

The Luminosity method is a more sophisticated version of averaging the red, green and blue. The method still uses an average but weights it to account for human perception. We're more sensitive to green, so green is weighted most heavily.

[256 colors]: https://jonasjacek.github.io/colors/
[256 colors json]: https://jonasjacek.github.io/colors/data.json
[luminosity method]: https://docs.gimp.org/2.6/en/gimp-tool-desaturate.html

## Testing and debugging

A version of the [ansi] bash script is provided for testing and
debugging convenience.

For example to preview every color code and it's generated color:

```sh
./bin/ansi --color-codes
```

Similarly to preview bold, underline, italic, etc:

```sh
./bin/ansi --color-table
```

[ansi]: https://github.com/fidian/ansi

## Attribution

Inspired by [vim-whitescale]

[vim-whitescale]: https://github.com/teoljungberg/vim-whitescale/
