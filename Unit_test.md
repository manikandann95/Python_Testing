unit test:

The most common type is a unit test.
Unit tests are used to verify that small isolated parts of a program are correct.

Unit tests are generally written alongside the code to test the **behavior of individual pieces** or units like functions or methods.
Unit tests help assure the developer that **each piece of code** does what it's meant to do.

Unit tests test the piece of code they target. An important characteristic of a unit test is **isolation**.

Given a known input, does the output of our code match our expectations? 

unittest module provides class TestCase to do our test cases.

**rearrange_test.py**
```Python
#!/usr/bin/env python3

from rearrange import rearrange_name #we are testing - class rearrange_name 
import unittest

class TestRearrange(unittest.TestCase): #TestCase is the class we need now
    def test_basic(self):
        testinput = 'LoveLace, Ada'
        expected = 'Ada LoveLace'
        self.assertEqual(rearrange_name(testinput), expected)


unittest.main()
```

**rearrange.py**
```Python
#!/usr/bin/env python3
import re

def rearrange_name(name):
    result = re.search(r"^([\w .]*), ([\w .]*)$", name)
    return "{} {}".format(result[2], result[1])
```

