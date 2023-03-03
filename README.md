# Laravel-s-Eloquent-ORM-where-a-specific-column-value-ends-with-a-hyphen-followed-by-numbers

Assuming you want to retrieve records from a database using Laravel's Eloquent ORM, where a specific column value ends with a hyphen followed by numbers, you can use the LIKE operator with a wildcard character % to match any characters before the hyphen and then specify a pattern to match the numbers after the hyphen.

Here's an example of how to do this:

```
$results = DB::table('my_table')
           ->where('my_column', 'LIKE', '%-%')
           ->where('my_column', 'REGEXP', '[0-9]+$')
           ->get();
```
In this example, my_table is the name of your database table, and my_column is the name of the column that you want to search.

The first where clause uses the LIKE operator to match any value in my_column that contains a hyphen. The % wildcard character matches any number of characters before the hyphen.

The second where clause uses the REGEXP operator to match any numbers that appear after the hyphen. The pattern [0-9]+$ matches one or more digits ([0-9]+) that appear at the end of the string ($).

Finally, the get method retrieves the results from the database and returns them as an array of objects.

Note: This approach assumes that the numbers following the hyphen are at the end of the string. If they can appear anywhere in the string, you'll need to modify the regular expression accordingly.
