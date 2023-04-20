This code is the D-Level Analyzer described in:

Lu, Xiaofei (2009). Automatic measurement of syntactic complexity in child language acquisition. International Journal of Corpus Linguistics, 14(1):3-28.

Version 2.1, released March 22, 2013

Copyright (C) 2013 Xiaofei Lu

This program is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation; either version 2 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program; if not, write to the Free Software Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA  02111-1307  USA

To download the latest version of this software, follow the appropriate link at
	http://www.personal.psu.edu/xxl13/download.html

==============================================================================
ABOUT

D-Level Analyzer is an automatic syntactic complexity analyzer based on the revised Developmental Level scale (Rosenberg & Abbeduto 1987; Covington et al. 2006). This analyzer assigns each sentence in an input text to one of eight levels, depending on the structure of the sentence.

To use the analyzer, the user needs to first tag a raw text using a part-of-speech tagger that follows the Penn Treebank tagging scheme and then parse the text using model 2 of Collins' parser. For information on downloading a tagger and the Collins' parser, see http://www.personal.psu.edu/xxl13/download.html

The analyzer is implemented in python and runs on UNIX, LINUX, or Mac OS X systems with emacs and python 2.5 or higher installed. The analyzer takes as input the output of Collins' parser (using model 2) and outputs a summary of the developmental levels of the sentences in the file. The analyzer references the regularized version of NOMLEX (Macleod et al. 1998) for nominalization recognition, which should be installed in the same directory as the analyzer. 

CONTENTS

[1] Running the code
[2] Input format
[3] Analyzing a single file
[4] Analyzing multiple files (with the .m2 suffix) in the same directory
[5] A list of the files included in this package

==============================================================================
[1] Running the code

To run the code:

python analyzer.py <input_file> <output_file>

There is a sample input file in the "examples" sub-directory. Run the following and check to see if examples/sample_output.txt is the same as examples/sample_scores.txt

python analyzer.py examples/sample_parsed.txt examples/sample_output.txt

==============================================================================
[2] Input format

The input file is the direct output of Collins' parser (using model 2). For an example, see examples/sample.m2

==============================================================================
[3] Analyzing a single file

To analyze a single file, type the following at the command line:

python d-level.py input_filename > output_filename

e.g., 

python d-level.py examples/sample.m2 > sample.d

The output will contain 2 lines. The first line is a comma-delimited list of field names: Filename, Sentences (number of sentences in the file), Level0 (number of Level 0 sentences in the file), ..., Level 7 (number of Level 7 sentences in the file), MeanLevel (the mean developmental level of the sentences in the file). The second line summarizes the results for the input file with a comma-delimited list of values that correspond to the list of fields in the first line.

 ==============================================================================
[4] Analyzing multiple files (with the .m2 suffix) in the same directory

To analyze multiple files (with the .m2 suffix) in the same directory, type the following at the command line:

python d-level-directory.py path-to-directory > output_filename

e.g., 

python d-level.py examples/ > results.d

The output format is the same as described in Section 3 above. The result for each .m2 file will be summarized in a separate line. 

==============================================================================
[5] A list of the files included in this package

README.txt - this file

d-level.py - the Developmental Level analyzer for a single file

d-level-directory.py - the Developmental Level analyzer for multiple files in a directory

NOMLEX-2001.reg - the regularized version of NOMLEX

examples/ - this directory includes a few example files:

sample.txt - a raw text file containing a short paragraph

sample.m2 - a parsed version (using model 2 of Collins' parser) of sample_text.txt 

sample.d - output of the D-Level analyzer for the file sample.m2

