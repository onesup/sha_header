[![Build Status](https://travis-ci.org/nbibler/sha_header.png?branch=master)](https://travis-ci.org/nbibler/sha_header)

# SHAHeader

SHAHeader is a simple Rack middleware gem for Rails 3.  When required, it
will instruct Rails to automatically insert its middleware into the Rack
stack and inject your current git SHA hash into all of your dynamic
response headers.

## Compatibility

The SHAHeader gem is Ruby 1.8.7, 1.9.2, 1.9.3, and 2.0.0 compatible and it is
compatible with Rails 3.x.

## Installation

In Rails 3, modify your `Gemfile` to add the following line:

    gem 'sha_header'

That's it.  It is distributed with a `Railtie` to instruct Rails on how
to set it up, so no other coding is required.

## Example

Here's a simple example for a Rails application running locally.  The
application has added the above `Gemfile` line.  Using curl:

    curl -I http://localhost:3000/

And, the following response is received:

    HTTP/1.1 200 OK 
    Content-Type: text/html; charset=utf-8
    ETag: "25ec427afba8daa376f309559b1b3c5c"
    Cache-Control: max-age=0, private, must-revalidate
    X-Git-SHA: 8c139c519c731be597d0c37a6e5ce46a27bab174
    X-UA-Compatible: IE=Edge
    X-Runtime: 0.120340
    Content-Length: 0
    Connection: Keep-Alive

(Notice the `X-Git-SHA` header)
