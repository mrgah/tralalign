# tralalign

# What is tralalign?

tralalign is a tool to facilitate the study of translations. It makes use of
[CollateX](https://collatex.net), but instead of collating textual sources, it
allows users to specify shared normalization values for texts in different
languages.

# What do I need to use tralalign?

tralalign requires Python 3, Jupyter Notebook, and several Python modules,
chief among which is collatex itself.

tralalign takes as its input texts in two different languages, which it
normalizes according to values in user-supplied CSV files. These CSV files
(which can be produced in Microsoft Excel and a number of other programs) need
to supply both individual words (tokens) and all-caps normalization values.

To align the beginning of Galen's *Ars Medica* and its Latin translation, for
example, the Greek normalization file would give Τρεῖς as the token and THREE
as the normalization value, while the Latin would give Tres as the token and
THREE as the normalization value. (Or, if you wanted to align Galen's text and
its Arabic translation, you can give ثلثة as the token and THREE as the
normalization value. Do note that Microsoft Office products do not always work
well with right-to-left languages.)

# How do I use tralalign within Jupyter Notebook?

Once you've started Jupyter Notebook, you simply call the function `tralalign`
with three values: the names of the CSV files and the names of the text
you want to align. For example, to align the Greek text of Galen's *Ars Medica*
and its Latin translation, you simply run the following in a Jupyter Notebook
cell:
`tralalign('gk','la','ars_medica')`

Note that this assumes that your CSV files are named `gk.csv`, `la.csv`, and that
the two files you wish to align are named `ars_medica-gk.txt` and
`ars_medica-la.txt`. (The values of the lg1file and lg2file variables can
also be easily modified.)

Within Jupyter Notebook, the script will then output an html table with the
two texts aligned by the normalization values specified in the CSV files. 
