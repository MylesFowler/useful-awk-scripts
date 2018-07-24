# useful-awk-scripts

#printing all columns in a file where tab is the delimiter of the input.
awk -F'\t' '{print $0}' file.txt

#printing all columns in a file where tab is the delimiter of the input and comma is the output field separator.
awk -F'\t' '{OFS=","; print $0}' file.txt

#Sum of a column where $1 is the column being summed.
awk -F'\t' '{sum += $1} END {print sum}' file.txt

#Getting the sum of a column based on a specific pattern in the data. $1 is the column.
awk -F'\t' '$1 ~ /^G01/ {sum += $16} END {print sum}' file.txt
