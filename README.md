# BEER-LAMBERT LAW
## presentdata.py

**Purpose**: present the data of intensity and wavelength for all concentrations for a specific material.

**Input**:
- A directory containing `.ods` spreadsheet files starting with a specific prefix (for example for Rhodamine 6G we used prefix `RG...`).
- each spreadsheet contains a column of wavelengths and a column of normalized intensity

**Output**:
- A matplotlib plot showing filtered spectra (but from wavelength ≥ 457 nm) from all matched `.ods` files, with each spectrum color-coded and labeled by filename.

**Relation to the article**:
- This plot will be shown in the beginning of the results paragraph.
- 
## integratecode.py

**Purpose**: calculates the integrated intensity using numerical trapezoidal integration.

**Input**:
- A single `.ods` file containing two columns: Wavelength (in nm) and Intensity (arbitrary units).

**Output**:
- A printed result in the format:  
  `Integrated intensity from 457 nm: [value] ± [error]`

**Relation to the article**:
- This script provides the quantitative measure of spectral intensity used in the results section to compare emission strength between samples. each output will be a dot.

## PartAFit

**Purpose**: to gather all the data of different concentrations of the same fluorophore, for all 3 fluorophores, and plot them on a graph. it will also fit a linear fit to each of them.

**Input**:
- a single excel file with 3 sheets, each sheet containing the data gathered in the integratecode.py code for different materials.

**Output**:
- a graph that presents both the data given in the input, and fits linear fit to each of the sheets. all will be presented on a single graph.

**Relation to the article**:
- this is the part where the beer lambert law states we are to get a linear fit in each of those sets. this is the main graph of this section.

## polynomialfit.py

**Purpose**: to fit a 3rd order polynomial to the 2 fluorophores that worked well in our experiment. integrated normalized intensity taken by log versus the concentration.

**Input**:
- an excel file containing 2 sheets, each sheet contains columns of concentration, and the integrated intensity for the 2 fluorophores.

**Output**:
- print the graph depicting the polynomial fit, the coefficients, and the chi squared reduced calculated.

**Relation to the article**:
- the idea in this fit is to show that a 3rd degree polynomial fits to our data better than linear fit, unlike what expected from the beer-lambert law.

## PartB.m

**Purpose**: anaylize the data from the photos taken with our personal phones.

**Input**:
- a .jpg (or .jpeg) file

**Output**:
- an array of x values
- an array of integrated normalized intensity taken by log values

**Relation to the article**:
- another way to fit to beer-lambert law. this time we also changed the path length and captured it with our phones. this code analyzes this data.

## bookfit.py

**Purpose**: after the PartB.m code returned us the arrays, this code fits the data according to beer-lambert law for each concentration.

**Input**:
- an excel file that contains 2 columns: x values, and integrated normalized intensity taken by log values
- a small region inside the data (to find a small linear-like region in order to fit)

**Output**:
- print the data, and fit a linear fit inside the region selected manually.
- print the coefficients of that linear fit, the chi squared reduced, and to calculate the molar absorption coefficient according to the linear region in the data.

**Relation to the article**:
- those molar absorption coefficients were averaged for each fluorophore over all the concentration, and presented at the end of the part.

# EXCITON-POLARITON

## peaksfinder

**Purpose**: to find the peaks in a measurement taken for different angles. it will fit a gaussian to the found peaks, and give back the fitted gaussian peak value and its error. it will also present the gaussians.

**Input**:
- an excel file containing 2 columns: wavelength and intensity.

**Output**:
- the fitted gaussians peak centers and errors
- the fitted gaussian on a graph compared to the real data

**Relation to the article**:
- those peaks will be taken and used to find the energies and wavenumbers, which will be used in out final fit.

## excitonfit.py

**Purpose**: Briefly describe what the script does.

**Input**:
- List the expected input files, variables, or parameters.

**Output**:
- Describe what the script produces (e.g., a plot, a CSV file, a printed result).

**Relation to the article**:
- Mention which part of the article this script supports or illustrates (e.g., "This script generates Figure 2 in the Results section").
