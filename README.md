# NAMiX

Nucleic acid modelling, including xeno-nucleotides, is a tool designed to simplify the preparation, building, and refinement of heavily modified nucleic acid structures for use with cryo-EM and X-ray structural maps.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Tested Versions

The code has been tested on the following systems:

### Ubuntu 22.04.3 LTS
- Python 3.10.2
- NumPy 2.1.1
- Perl 5.34.0

### Windows 11 (26200.8037)
- Python 3.14.3
- NumPy 2.4.4

## Installation

Download the code from GitHub or clone the repository into your desired location.

```bash
git clone https://github.com/esa-lab/NAMiX.git
```

Add the NAMIX folder to your `PATH`.

NAMIX is intended to be run from the directory containing your structure files and maps. Adding the installation directory to your `PATH` allows the program to be called from any working directory.

### Linux

Add the following line to your `.bashrc` file (or the equivalent configuration file for your shell):

```bash
export PATH="path_to_namix_folder:$PATH"
```

### Windows

Open **"Edit the system environment variables"** and add the NAMIX folder to the `PATH` variable.

### Using ROAD-style blueprints

If you want to use ROAD-style blueprints for generating base-pair restraints, Perl must be installed in addition to Python. The blueprint-to-dot-bracket conversion code is adapted from the [ROAD](https://github.com/esa-lab/ROAD) repository.

## Usage

NAMIX currently supports the legacy `.PDB` format and does not support the newer `.cif` format.

Your data files do not need to be located in the NAMIX installation directory. However, your terminal working directory should be the directory containing the data being processed.

Run NAMIX using:

```bash
namix -f [filename] [options]
```

To display all available options:

```bash
namix -h
```

The `-f [filename]` argument is the only mandatory parameter.

### Options

```text
-r [file]   Use a Chimera .pb file to generate base-pair restraints
            for use with a Phenix .eff file.

-b [file]   Generate restraints from a ROAD blueprint
            for use with a Phenix .eff file.

-p [prefix] Add file prefixes and folder suffixes.

-o          Overwrite existing folder contents.

-v          Convert modified nucleotides back to RNA.

-m          Output only the modified PDB file and any
            generated restraints.
```

### Applying Modifications

Modifications are specified using the following format:

```text
-[base_to_replace] [modification_3_letter_code,resid,resid,...]
```

If no residue IDs are provided, all residues of that base type will be replaced.

```text
-a [modification,resids]  Set modification for adenine.
-c [modification,resids]  Set modification for cytosine.
-g [modification,resids]  Set modification for guanine.
-u [modification,resids]  Set modification for uracil.
-t [modification,resids]  Set modification for thymine.
```

## Contributing

1. Create a new branch:

```bash
git checkout -b feature-name
```

2. Make your changes.
3. Push your branch:

```bash
git push origin feature-name
```

4. Create a pull request.

## License

This project is licensed under the GPL-3.0 license. See the LICENSE file for details.
