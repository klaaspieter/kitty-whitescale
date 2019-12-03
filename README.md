# Kitty whitescale

A whitescale colorscheme meant to keep its colors in white, black, and gray.

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

3. Add this line to your kitty.conf configuration file:

```sh
include ./theme.conf
```

## Building from source

The script in `./bin/generate` automatically generates the kitty config. It does so by taking [this list of 256 (Xterm) colors][256 colors] ([json][256 colors json]). It applies the [luminosity method] to each color which results in a set of grayscale colors.

The luminosity method:

```
Luminosity = 0.21 × Red + 0.72 × Green + 0.07 × Blue
```

The Luminosity method is a more sophisticated version of averaging the red, green and blue. The method still uses an average but weights it to account for human perception. We're more sensitive to green, so green is weighted most heavily.

Print the config to the console

```sh
./bin/generate
```

Or write it to a file

```sh
./bin/generate > test.theme
```


[256 colors]: https://jonasjacek.github.io/colors/
[256 colors json]: https://jonasjacek.github.io/colors/data.json)
[luminosity formula]: https://docs.gimp.org/2.6/en/gimp-tool-desaturate.html

## Attribution

Inspired by [vim-whitescale]

[vim-whitescale]: https://github.com/teoljungberg/vim-whitescale/
