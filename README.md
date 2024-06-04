<img src="doc/proteosynth-logo.png" width="250">

## ProteoSynth: A tool for testing proteomics analysis pipelines against ground truth

ProteoSynth generates synthetic LC-MS data in mzML format. It is intended to be used to test data processing pipelines against ground truth.

Please note that this is an alpha release of the tool for interested members of the community. We are using the tool internally to validate
protein abundance quantification methods, but there are a plethora of other possible applications, and we're happy to get feedback on its utility
from users interested in adopting it for their proteomics analysis pipelines.

You may want to take a look at our [ASMS 2024 Poster](doc/ASMS-2024-Poster.pdf).

### Installation

ProteoSynth is currently released as a self-contained binary command line tool for Windows, Linux, and OSX.
Visit the [Releases page](https://github.com/ngenebio-ai/proteosynth/releases) and download the binary for your platform and the model archive.
Put the binary somewhere in your path, and unzip the models archive wherever you like (you'll have to configure their location later).

### Protein abundances

To generate a CSV file specifying protein abundances from a FASTA file, run

    ProteoSynth -i proteins.fasta -o proteins.csv

### Synthesis configuration

ProteoSynth's synthesizer is configured with a single JSON file and the collection of models downloaded with the binary.

To generate a default configuration file, run

    ProteoSynth -o config.json

You can then edit the various options in the file prior to synthesis.

### Synthesis

Once happy with the configuration, to synthesize a run, use

    ProteoSynth -c config.json -o run.mzML

Use the `-p` option to modify the abundance of a set of proteins without regenerating your proteins.csv file. Use the `-d` option to simulate DDA mode rather than DIA.

Those are the basics. We will add further details and examples here soon!
