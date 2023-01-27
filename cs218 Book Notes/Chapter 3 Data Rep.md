	- Refers to how information is stored within the computer
	- Methods for storing ints vs floats vs ascii, etc


#### 3.1 Int Representation
	- This is how ints are stored in a computer
	- limited by the bit as 1/0 are base 2, not base 10
	- Must use larger number of bits to represent larger #s


##### Twos Compliment, other data manipulation page 23+


#### 3.3.3 Not a Number (NaN)
	- incorrect format or unrepresentable number is referred to as a NaN

#### 3.4 Chars and Strings
	- Symbolic data is represented by assigning numeric values to each character
	- ie ASCII

#### 3.4.1 Character Representation
	- Characters are units of information that correspond to a symbol
	- this can be letters, digits, punctuations and whitespace

#### 3.4.1.1 American Standard Code for Information Interchange
	-  World decided that they would be weird together and thus it became normal
	-  Characters have numeric values, those values correlate to symbols
	- Characters can also represent integars but cannot be used in calculations

#### 3.4.1.2 Unicode
	- Unicode is the current standard that includes support for different languages
	- Provides different encoding systems to provide unique number to EVERY char
	- most common encoding UTF-8 and ASCII are the same

#### 3.4.2 String Representation
	- Strings is a series of Ascii chracters
	- Typically terminated with a NULL
	- NULL is non-printable ASCII control char
	- Example
		- "H E L L O NULL"