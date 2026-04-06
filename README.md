# NAMiX
Nuclic acid modelling including xeno-nucleotide is a tool made to make the process of building and refiment of heavly modifed neclic acids stctures into strucule maps.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)


## Tested versions
The code is tested on python version 3.10.2,3.14.3
The code uses numpy and have been tested on version 2.1.1
The trace_pattern.pl code uses perl and have been tested with version 5.34.0

The code have been tested on the following operation systems:
 Windows 11
 Ubuntu 22.04.3 LTS

## Installation

Download the code from github or clone the git repository into the wanted location.
```bash
 git clone https://github.com/esa-lab/NAMiX.git
```

After this add the NAMIX folder to your PATH
Adding NAMIX to PATH is need as the code is intened to operrate in the folder with the data so it need to be assasiable from any directory/folder.

### Linux:
Add the follwing to your .bashrc file or the equilant for other shells.
```bash
 export PATH="path_to_namix_folder:$PATH"
```
### Windows
Edit the system enveriment variables to add the NAMIX folder to PATH

### If using ROAD style blueprint
If you want to use ROAD style blueprints for the generation of base paring restraints. you need to have perl install in addtion to python, as the code for convereting the blueprint to dot-barcket format, is taken from the [ROAD](https://github.com/esa-lab/ROAD) repository.

## Usage
NAMIX can be called by just writting the following:

```bash
namix -f [filename] [options]
```
use the following to get the following list of options.
```bash
namix -h
```

The -f [filename] is the only part that is mandatory

For a list of options see below
-r [file]: .pb from chimira to gennerete basepair restrains for use in phenix with .eff file. \
-b [file]: make file for restrints based on ROAD blueprint for use in phenix with .eff file.
                  
-p [prefix]: for giving files prefixes and folder suffix

-o: for overwrite folder content with same name.\
-v: return mod nuc stucture to RNA.\
-m: Make NAMiX output only the modded pdb file and restrint if given.\

Mods are in the format "-[base to replace see below] [modifcation_3_lettercode,resid,resid....]"\
if no res ID is given all bases of the type will be replaced                  
                  
 -a [modifcaiton,resids]: set modifcation for adenine\
 -c [modifcaiton,resids]: set modifcation for cytosine\
 -g [modifcaiton,resids]: set modifcation for guanine\
 -u [modifcaiton,resids]: set modifcation for uracil\
 -t [modifcaiton,resids]: set modifcation for thymine

## Contributing
1. Create a new branch: `git checkout -b feature-name`.
2. Make your changes.
3. Push your branch: `git push origin feature-name`.
4. Create a pull request.

## License
This project is licensed under the [GPL-3.0 license](LICENSE).
