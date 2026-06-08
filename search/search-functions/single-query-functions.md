# Single query functions

| Function        | Description                                     | Usage                                                                                                                              |
| --------------- | ----------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| $eq             | Is equal to a given value.                      | `"$eq":[<field_name>,<value>]`                                                                                                     |
| $contains       | Contains a given value.                         | `"$contains":[<field_name>,<value>]`                                                                                               |
| $neq            | Is not equal to a given value.                  | `"$neq":[<field_name>,<value>]`                                                                                                    |
| $ncontains      | Does not contain a given value.                 | `"$ncontains":[<field_name>,<value>]`                                                                                              |
| $range          | Contains value in a given range of values.      | `"$range":[<field_name>,<lower_value>, <upper_value>,<lower_inclusive>,<upper_inclusive>]`                                         |
| $gt             | Is greater than a given value.                  | `"$gt":[<field_name>,<value>]`                                                                                                     |
| $gte            | Is greater than or equal to a given value.      | `"$gte":[<field_name>,<value>]`                                                                                                    |
| $lt             | Is less than a given value.                     | `"$lt":[<field_name>,<value>]`                                                                                                     |
| $lte            | Is less than or equal to a given value.         | `"$lte":[<field_name>,<value>]`                                                                                                    |
| $eq\_any        | Is equal to any value in a list of values.      | <p><code>"$eq_any": [</code> </p><p><code>&#x3C;field_name>, [&#x3C;value1>, &#x3C;value2>, ...]</code> </p><p><code>]</code></p>  |
| $contains\_any  | Contains any value in a list of values.         | <p><code>"$contains_any":[</code></p><p><code>&#x3C;field_name>,[&#x3C;value1>,&#x3C;value2>,...]</code></p><p><code>]</code></p>  |
| $eq\_none       | Is not equal to any value in a list of values.  | <p><code>"$eq_none":[</code></p><p><code>&#x3C;field_name>,[&#x3C;value1>,&#x3C;value2>,...]</code></p><p><code>]</code></p>       |
| $contains\_none | Does not contain any value in a list of values. | <p><code>"$contains_none":[</code></p><p><code>&#x3C;field_name>,[&#x3C;value1>,&#x3C;value2>,...]</code></p><p><code>]</code></p> |
| $eq\_all        | Equals all values in a list of values.          | <p><code>"$eq_all":[</code></p><p><code>&#x3C;field_name>,[&#x3C;value1>,&#x3C;value2>,...]</code></p><p><code>]</code></p>        |
| $contains\_all  | Contains all values in a list of values.        | <p><code>"$contains_all":[</code></p><p><code>&#x3C;field_name>,[&#x3C;value1>,&#x3C;value2>,...]</code></p><p><code>]</code></p>  |
