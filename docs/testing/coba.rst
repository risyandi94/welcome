Testing Document
================

* List 1
* List 1
* List 1
* List 1
* List 1

he first line simply tells that the source code is written for
Solidity version 0.4.0 or anything newer that does not break functionality
(up to, but not including, version 0.5.0). This is to ensure that the
contract does not suddenly behave differently with a new compiler version. The keyword ``pragma`` is called that because, in general,
pragmas are instructions for the compiler about how to treat the
source code (e.g. `pragma once <https://en.wikipedia.org/wiki/Pragma_once>`_).

A contract in the sense of Solidity is a collection of code (its *functions*) and
data (its *state*) that resides at a specific address on the Ethereum
blockchain. The line ``uint storedData;`` declares a state variable called ``storedData`` of
type ``uint`` (unsigned integer of 256 bits). You can think of it as a single slot
in a database that can be queried and altered by calling functions of the
code that manages the database. In the case of Ethereum, this is always the owning
contract. And in this case, the functions ``set`` and ``get`` can be used to modify
or retrieve the value of the variable.