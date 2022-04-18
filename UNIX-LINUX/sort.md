# SORT

> <b>sort +n1 -n2 file_name</b>

+n1 - no of rows to be skipped to get <b>START</b>
-n2 - no of rows to be skipped to get <b>END</b>

|       | 1   | 2   | 3   | 4   | 5   | 6   | 7   |
| ----- | --- | --- | --- | --- | --- | --- | --- |
| +0 -1 | &   |     |     |     |     |     |     |
| +2 -4 |     |     | &   | &   |     |     |     |
| +3    |     |     |     | &   | &   | &   | &   |

> Sorts row based on & marked columns  
> without options: string based  
> -n : to do ascending order

-m : to merge sorted files
-u : eliminate the duplicate lines after sorting
-r : reverse sorting
-d : dictionary sorting (special characters first)
-f : fold lowercase - upper and lower case are sorted together
