[:var_set('', """
# Compile command
aoikdyndocdsl -s README.src.md -n aoikdyndocdsl.ext.all::nto -g README.md
""")
]\
[:HDLR('heading', 'heading')]\
# AoikEnum
Enumeration for Python.

Tested working with:
- Python 2.7 and 3.5

## Table of Contents
[:toc(beg='next', indent=-1)]

## Setup
[:tod()]

### Setup via pip
Run:
```
pip install git+https://github.com/AoiKuiyuyou/AoikEnum
```

### Setup via git
Run:
```
git clone https://github.com/AoiKuiyuyou/AoikEnum

cd AoikEnum

python setup.py install
```

## Usage
Take int enumeration for example:
```
from aoikenum import enum


# ----- Create enumeration class -----
@enum
class Value(int):
    """
    Enumeration class.
    """

    ONE = 1
    TWO = 2


# ----- Use enumeration instance -----
assert Value.ONE == 1
assert Value.ONE.name == 'ONE'
assert repr(Value.ONE) == 'ONE'

assert Value.TWO == 2
assert Value.TWO.name == 'TWO'
assert repr(Value.TWO) == 'TWO'

# ----- Create enumeration instance from enumeration value -----
one = Value(1)
assert one == Value.ONE
assert one.name == 'ONE'
assert repr(one) == 'ONE'

two = Value(2)
assert two == Value.TWO
assert two.name == 'TWO'
assert repr(two) == 'TWO'

# ----- Create enumeration instance from enumeration instance -----
one = Value(Value.ONE)
assert one == Value.ONE
assert one.name == 'ONE'
assert repr(one) == 'ONE'

two = Value(Value.TWO)
assert two == Value.TWO
assert two.name == 'TWO'
assert repr(two) == 'TWO'

# ----- Create enumeration instance from invalid value -----
zero = Value(0)
# ValueError: Invalid value: 0
# Valid values:
# Value.ONE == 1
# Value.TWO == 2
```
