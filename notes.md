# What's New
## [Python 3.8 Features](https://docs.python.org/3/whatsnew/3.8.html)
- Assignment Expressions
    - Walrus operator := can be used to assign a value to a variable within an expression. Common use case is when checkin the result of an expression, and based on the result, using the result of the expression.
        - e.g.
            ```
            discount = 00
            if (re.search(r'(\d+)% discount', advertisement)):
                discount = float(re.search(r'(\d+)% discount', advertisement).group(1)) / 100.0
            ```
            vs.
            ```
            discount = 00
            if (mo := re.search(r'(\d+)% discount', advertisement)):
                discount = float(mo.group(1)) / 100.0
            ```
- Self-documenting f-strings
    - f-strings can now include an equal sign after a variable name to automatically expand into the form: <variable>=<value of variable>
        - e.g.
        ```
        >>> var = 'some test data'
        >>> f'{var=}'
        "var='some test data'"
        ```

- Positional only parameters
    - Forward-slash character in a function signature indicate that any arguments preceding it cannot be specified by key-value pairs, but will be interpreted by position only
    - Following, an asterisk character indicates taht arguments between the forward-slash and asterisk can be either positional or keyword, and those after the asterisk must be keyword arguments
    - e.g.
        ```
        def func(a, b, /, c, d, *, e, f):
            pass
        ```
        In the above function, a and b must be positional arguments, e and f must be keyword arguments, and c and d may be either



## [Python 3.7 Features](https://docs.python.org/3/whatsnew/3.7.html)
- Postponed Evaluation of Annotations
    - Change to how annotations are implemented, meaning it is now possible to use type-hinting within a class, and reference that class as an input/return type itself.
    Note: This will require the following import:
        ```
        from __future__ import annotations

- New breakpoint() function added to enter debugger

## [Python 3.6 Features](https://docs.python.org/3/whatsnew/3.6.html)
- f-strings 
    - f-strings introduced to allow easier string formatting
        - See [Formatting Documentation](https://docs.python.org/3/library/string.html#formatspec) for more

- Type-hinting added for variables
    - e.g.
        ```
        primes: List[int] = []
        ```

- Underscores in Numeric Literals
    - Single underscores can be used in numeric literals to improve readability
        - e.g.
            ```
            >>> 1_000_000_000
            1000000000
            >>> 0x_FF_FF_FF_FF
            4294967295
            ```

## [Python 3.5 Features](https://docs.python.org/3/whatsnew/3.5.html)
- Type hinting added
    - See [PEP 483](https://www.python.org/dev/peps/pep-0483/)

Type Hinting

Import System
- Finders, Loaders etc.
- sys.moduless
- \_\_all\_\_
- \_\_package\_\_
- \_\_name\_\_
- \_\_init\_\_.py
- \_\_main\_\_.py
- \_\_module\_\_


\_\_slots\_\_ (See example [here]https://www.python.org/download/releases/2.2.3/descrintro/#subclassing))
- Special attribute that reserves space in an instance for only the given instance variables
- No other instance variables can be assigned to
- Used for memory savings in cases where there will be a large number of instances of the class created

Class system
- Old vs. New style classes in Python 2 (default to New in 3)
- Defining a class with type()
- PyObject structure
- underscore and double underscore and name mangling
- \_\_init\_\_
- \_\_new\_\_
