# rpReader

Given a list of heterologous pathways generated by RetroPath2.0, and enumerated by rp2paths, this tool converts the pathways to individual enriched SBML files (that we refer to as rpSBML files). These contain the standard SBML required information to describe a metabolic network, but includes infomation on the structure of the chemical species as well as more description of the reactions.

## Information Flow

### Input

Required information:
* **RP2paths Pathways**: The enumerated pathways by the rp2paths nodes
* **RP2paths Compounds**: The list of compounds produced by the rp2paths nodes
* **RetroPath2.0 Pathways**: The original list of pathways produced by rp2paths

Advanced options:
* **out paths max number of substeps per step**: (default: 2) A reaction rule may have multiple reactions assovciated with it. This number determines the depths of rules to use (ranked by score) to calculate the possible subpaths.   
* **SBML compartment ID**: (default: MNXC3) The default ID refers to the cytoplasm.
* **rpSBML path ID**: The pathway ID to be used to identify the heterologous reactions and chemical species.
* **Server URL**: The IP address of the REST service.

NOTE: The calculated rp2paths pathways and compounds must be generated using the same "RetroPath2.0 Pathways" file as input here.

### Output

* **rpReader**: Collection of rpSBML files archived in a tar.xz. 

## Installing

To build the image, use the Dockerfile using the following command:

```
docker build -t brsynth/rpreader-rest -f Dockerfile .
```

To run the service on the localhost as the Galaxy instance run:

```
docker run -p 8886:8888 brsynth/rpreader-rest:dev
```

### Prerequisites

* [Docker](https://docs.docker.com/v17.09/engine/installation/)
* [libSBML](http://sbml.org/Software/libSBML)
* [RDkit](https://www.rdkit.org)

## Contributing

TODO

## Versioning

Version 0.1

## Authors

* **Melchior du Lac**

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Thomas Duigou
* Joan Hérisson

### How to cite rpReader?

TODO
