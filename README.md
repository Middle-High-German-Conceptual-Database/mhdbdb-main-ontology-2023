# dhPLUS Ontology

This directory contains all sources of the dhPLUS ontology.

## Template Usage

The build process allows the usage of templates in .ttl files. Tags are marked with {{ }}.

|Tag                        |Function|
|---	                    |---	|
|{{ modificationDate }}     |Inserts the date of the last commit for the file in format *YYYY-mm-dd+HH-MM* (xsd:date).|
|{{ sparql }}| Inserts the content of a .sparql file of the same name (without extension) as the .ttl file and lying in the same directory.|
|{{ sparqlBlocks.$blockName }}|Inserts the content of a $blockName.sparql file located in the sparqlBlocks directory.|
|{{ endpoint.$endPointName }}|Inserts the uri of a sparql endpoint specified in config.json of repository.|

## Build

### Preparations

Add configuration into 'empty.config.json' and save as 'config.json'

#### Setup Python3 venv

On your machine, Python 3.6 or higher needs to be installed. Installation instruction can be found [here](https://www.python.org/download/releases/3.0/).

After installing, generate virtual environment via console in project folder. All commands have to be executed from the projects main directory.

```console
$ python3 -m venv venv
```

Your environment should have been generated locally in _dhplus-models/venv/_. That folder won't be added to the .git repository.

To add all needed libraries, you need to activate you environment first:

*Linux*

```console
$ . venv/bin/activate
```

*Windows*

```console
$ .\/venv/Scripts/Activate.ps1
```

After activation you should see _(venv)_ in front of your active terminal line.

##### Install required external libraries

You need to load all needed libraries with

```console
(venv)$ pip3 install -r requirements.txt
```

##### Install dhpt library

Clone repository *dhplus_python_tools*. Navigate to repo in console and install with pip

```console
(venv)$ pip3 install -e .
```



#### Needed tools

##### TopBraid SHACL API

See [Documentation](https://github.com/TopQuadrant/shacl) for detailed installing instructions. Needs to be added to *PATH*.

##### Add to Path (Linux)

```console
$ export SHACLROOT=[your shacle directory]/bin/
$ export PATH=$SHACLROOT:$PATH
```

###### Widoco

Download .jar from [Repository](https://github.com/dgarijo/Widoco) and modify path in config.json.
