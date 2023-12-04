# Get C's scanf alike function in Python

## Available identifiers
| Conversion Specifier | Meaning                                   |
|----------------------|-------------------------------------------|
| `%d`                 | Integer. Matches an optionally signed decimal integer. |
| `%f`                 | Floating-point number. Matches an optionally signed floating-point number, possibly in exponential notation. |
| `%s`                 | String. Matches a string with or without whitespaces. Also works for characters. |

If you need more identifiers it's really easy to add since under the hood it's just plain regex.


## Usage

To use the `scanf` function, import it from the module and call it with a pattern and an input string. The function will parse the input based on the pattern and **returns a tuple of values, each cast to its corresponding type**.

### Example
I created this function because it mainly comes in handy in Advent of Code problems. Taking for example [Day 5 - AoC 2022](https://adventofcode.com/2022/day/5) parsing the input is just:

```python
from scanf import scanf 

pattern = "move %d from %d to %d"
input_string = "move 2 from 4 to 1"
result = scanf(pattern, input_string)

print(result)  # Output: (2, 4, 1)
print(all(isinstance(item, int) for item in result)) # True
