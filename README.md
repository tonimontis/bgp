[![Build Status](https://travis-ci.org/miekg/bgp.svg?branch=master)](https://travis-ci.org/miekg/bgp)

# BGP

BGP is a BGP-4 implementation in Go.

## RFCs

* BGP Communities: <https://tools.ietf.org/html/rfc1997>
* Capabilities Advertisement with BGP-4: <https://tools.ietf.org/html/rfc3392>
* BGP-4: <https://tools.ietf.org/html/rfc4271>
* BGP Extended Communities: <https://tools.ietf.org/html/rfc4360>
* BGP 32 bit AS numbers: <https://tools.ietf.org/html/rfc4893>
* BGP 32 bit AS numbers: <https://tools.ietf.org/html/rfc6793>


## Notes

Parameters in the open message seems not to be used. Can hide it
in its entirety and just focus on capabilities. i.e make Append()
work on the open message itself.

Also the data in now a []TLV, maybe it would be nicer to have a
map map[int]TLV indexed on the Code so we can implement a .Clear(code int)
as well to clear a message.

## TODO

* multiple message after each other, i.e. Open and Notifcation.
* fix all error uses
* create server infra ala net/http, godns
* Fix Path Attributes, these are like dns RR's, define an interface
    and use reflection to pack/unpack.
* Unpack doesn't do header, Pack does do header
    Makes more sense if they *all* do or neither.
* Tests!
