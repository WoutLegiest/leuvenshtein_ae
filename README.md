# Artifact Evaluation Levenshtein-Trinary - Leuvenshtein

## Building guidelines

First, install Rust; [https://www.rust-lang.org/tools/install](https://www.rust-lang.org/tools/install)
`curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`

The project is run using rustc v1.80. To install this specific rust version with
`rustup install 1.80.0`

- Make a temp directory and go to that directory
- Run `cargo init`; this will initialise a rust project
- Overwrite the `Cargo.toml` file with the one found in this repository
- Overwrite the main file, located at `src/main.rs`, with the one found in this repository
- Add the `main_prepros.rs` file to the `src` folder

The programs can now be run with

- `cargo run --release` to run the main algorithm
- `cargo run --release --bin leuvenshtein_prepross` to run the preprocessing variant

## Select size

At the start of the main function -- `fn main()` -- you can select the input string size by uncommenting the desired size.

## Running the Concrete (Compiler) Implementation

- Install the concrete library:
  `pip install concrete-python==2.8.1`
- Clone the correct Concrete version
  `git clone https://github.com/zama-ai/concrete ; cd concrete ; git reset --hard fd9db128869818293d3b4336f44e5938cfe5c480`
- Copy the patch file to the folder and apply our patch to the repo:
  `git apply concrete_ascii.patch`
- Go to Levenshtein distance folder:
  `cd frontends/concrete-python/examples/levenshtein_distance/`
- Run the wanted size of concrete instance
  - `python3 levenshtein_distance.py --distance abcdefgh adcdefgf --alphabet ascii --max_string_length 8`
  - `python3 levenshtein_distance.py --distance BEgfEHGfShHtvKazXNeEvNWmvfbrAWyAYZjkXvNkmEajQNCTKZnkPeEDadvQtUnGhJRpWZASUMfXArGZFSUYgFeCAWxSvKNdpsnV EEhjZMnFsMFCsKnnyZvtrPeKxfmJfJVJNcYAwYmrGNgTUUSAgduNQZttWFdYFKddcKjkUEpPUmGkszZSVVNWkThxSFRgMzrbqATe --alphabet ascii --max_string_length 100`
  - `python3 levenshtein_distance.py --distance mizf30WE1Pzqu0HtZKMMCE6f3NE2TGPPYmgSunfkBJqGJqveg97i61fu5KG7z8UmR5DVVALk5CCL0fzEv687LdRuunZ8SYUFmQEf66dXZ6vejGKR7HhSiY5XLWbCYFddqtFEX2QjmHRmqB7tngfG7m0CBX1D6wcvLyYp0rpiv1GSw5T1ZfuT2mcjHUi05zd6N4EqLmTP8ETEc2vQaJcVGSaXRETejNebwwb4m9wUUMd0abrEQeLw3Ubn9un6tTeP yVL0hi1V8mUQakFWZGEHwQBduvaTtKC6dNMbnyEiU29pKdwLfCnY7jWceXQizTiwhGxiAkuwvdcgpTtaZW3XJ6t75HL86nV2QPUWaxipf6x7JE8NPQT0RrzcheaydjLdPyUhAQ3UhJ2bLVE5wtNDAgdBgX3N5Ru4iXqbFXWD5ZAbzniVaWr5iE0wQenwt8QjqERf6A67P9rLkmGPKS8LHJxttCKRBWM3qr1F93JZtEhGKcQ1079pUXcCgAvLhCWi --alphabet ascii --max_string_length 256`
