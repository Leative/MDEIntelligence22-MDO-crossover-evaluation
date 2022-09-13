# Explanation of collected data

## Archive file
A 7z archive file can be found in the release section of the Github repository. It contains the raw output data of MDEOptimiser for all experiments. Despite its rather small size the extracted data needs about a gigabyte of disk space.
In the archive, for each evolutionary computation (called **batch**) a file `batch-\<batchNumber\>-data-steps.csv` is provided containing data about the elapsed time, the population and the non-dominated solutions of each iteration of the batch.
A file `**batch-\<batchNumber\>-outcome.txt` contains a summary including more information about the non-dominated solutions of the last iteration. Note that correctly tracking data about parent mutation steps and transformation chains in the presence of crossover has not yet been implemented; thus, the tracked data is invalid.

## Analysis folders
The analysis folders contain data collected by an analytical tool from the output of MDEOptimiser.
Each folder contains a summary report for all problem instances which gives an overview over the most important metrics:
- the mean number of iterations,
- the mean time needed per iteration in milliseconds,
- different aggregations of the normalized hypervolume, and
- the standard deviation for the mean normalized hypervolume.
Additionally, for each problem instance an overview over some statistical values is provided in a separate file. They need to be read as row x column, i.e., a positive value for Cliff's delta means that the variant in the header of the respective row performs better than the variant in the header of the respective column.

A separate folder for each problem instance contains more in depth information about the performed evolutionary computations. The names of the files are chosen to be self-explanatory.

As the hypervolume is normalized according to all the solutions found for a specific problem instance, the results of an analysis depend on which variants are considered in the analysis.
Therefore, we include two analysis folders:
- In `analysis-all` all variants we ran experiments on are compared with each other.
- In `analysis-paper` only the variants shown in the paper are compared.
