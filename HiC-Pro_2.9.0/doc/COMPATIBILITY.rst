.. _COMPATIBILITY:

Compatibility with other software
=================================

| HiC-Pro is designed to process Hi-C data from .fastq files to normalized contact matrices. Additional software or methods should then be used to perform downstream analysis. We therefore decided to propose several utilities to increase the compatibility of HiC-Pro with other tools. Most of the scripts presented below were developed by HiC-Pro users or collaborators. Many thanks to them for sharing their work with us, and do not hesitate the contact us with many new ideas !

Juicebox visualization software
-------------------------------

The `Juicebox<http://aidenlab.org/juicebox/>`_ software allows dynamic visualization of HiC contact maps. The list of valid interaction products called by HiC-Pro can can be converted in Juicebox input format (.hic file). To do so, please have a look at the hicpro2juicebox.sh utility.


HiCPlotter visualition software
-------------------------------

The output format of HiC-Pro can be loaded into the `HiCPlotter<https://github.com/kcakdemir/HiCPlotter>`_ software for Hi-C data visualization.
Here is a small example of how to use it.

.. code-block:: guess

   ## Plot the genome-wide map at 1Mb resolution
   python HiCPlotter.py -f hic_results/matrix/sample1/iced/1000000/sample1_1000000_iced.matrix -o Examplegw -r 1000000 -tri 1 -bed hic_results/matrix/sample1/raw/1000000/sample1_1000000_ord.bed -n hES -wg 1 -chr chrX

   ## Plot the chrX at 150Kb resolution
   python HiCPlotter.py -f hic_results/matrix/sample1/iced/150000/sample1_150000_iced.matrix -o Exemple -r 150000 -tri 1 -bed hic_results/matrix/sample1/raw/150000/sample1_150000_ord.bed -n Test -chr chrX -ptr 1

TADs calling (Directionality Index)
-----------------------------------

TADs calling is frequently run on Hi-C data at a 40Kb or higher resolution. In order to run the first method proposed by Dixon et al., you can generated the input file using the sparseTodense.py utility.

Fit-Hi-C
--------

`Fit-Hi-C <https://bioconductor.org/packages/release/bioc/html/FitHiC.html>`_ is a popular approach to detect significant interaction on intra-chromosoml contact map.
Please use the hicpro2fithic.py utility to connvert HiC-Pro output to Fit-Hi-C input files.

R and HiTC BioConductor package
-------------------------------

The `HiTC <https://bioconductor.org/packages/release/bioc/html/HiTC.html>`_ package proposes function to import HiC-Pro output into the R environment.
Contact matrices are then stored as sparse Matrix, which can be used for any downstream analysis.

