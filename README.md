# NLTE_corrections
Using machine learning neural network trained on Fe data, calculate Fe1 and Fe2 NLTE corrections

 ---

1. Running the script
2. Dependencies
3. Using only ´function_aberr.py´

 ---

## 1. Running the script

### 1.1 Prepare the input file

The input file contains information about the lines for which the NLTE corrections ´aberr´ is calculated and has the following syntax


    # teff/K, lg(g/cms^-2), [M/H], vmic/kms^-1,   Elo/eV,        Eup, l.   ggf, Species
    5051.0,           4.0,   4.5,          0.0,  2.998045,  5.586893, -2.56300,     Fe1

For an example input file, ´see test_data.csv´. 

### 1.2 Running the script

This is a ´python3´ script, that takes (obligatorily) 2 input, the ´input_file.csv´ filename, and ´output_file.csv´ filename as

    python3 main_aberr.py input_file.csv ouput_file.csv


### 1.3 Running the script

The output will have the similar syntax to the input file, with added columns:

- The first column is an index column - int value
- The aberr column contains the calculated NLTE corrections - float value
	- If the input values are outside the stellar parameter grid, of the species is wrong, this value is a defalt -999 value
- The extrapolation column states if extrapolation is allowed - True/False
- The in_grid column states if the stellar parameter is within the model grid values - True/False