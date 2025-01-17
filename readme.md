<a href="https://golang.org"><img src="https://img.shields.io/badge/powered_by-Go-3362c2.svg?style=flat-square" alt="Built with GoLang"></a>


# Surveillance

This is the source code for the intern project Working with Websockets in Go (Golang).

A monitoring service, intended to replace things like Nagios.

## Build

Build in the normal way on Mac/Linux:

~~~
go build -o surveillance cmd/web/*.go
~~~

Or on Windows:

~~~
go build -o surveillance.exe cmd/web/.
~~~

Or for a particular platform:

~~~
env GOOS=linux GOARCH=amd64 go build -o surveillance cmd/web/*.go
~~~

## Requirements

Surveillance requires:
- Postgres 11 or later (db is set up as a repository, so other databases are possible)
- An account with [Pusher](https://pusher.com/), or a Pusher alternative 
(like [ipê](https://github.com/dimiro1/ipe))

## Run

First, make sure ipê is running (if you're using ipê):

On Mac/Linux
~~~
cd ipe
./ipe 
~~~

On Windows
~~~
cd ipe
ipe.exe
~~~

Run with flags:

~~~
./surveillance \
-dbuser='mehmetkaralar' \
-pusherHost='localhost' \
-pusherPort='4001' \
-pusherKey='123abc' \
-pusherSecret='abc123' \
-pusherApp="1" \
-pusherSecure=false
~~~~

## All Flags


Usage of ./surveillance:
  -db string
        database name (default "surveillance")
  -dbhost string
        database host (default "localhost")
  -dbport string
        database port (default "5432")
  -dbssl string
        database ssl setting (default "disable")
  -dbuser string
        database user
  -domain string
        domain name (e.g. example.com) (default "localhost")
  -identifier string
        unique identifier (default "surveillance")
  -port string
        port to listen on (default ":4000")
  -production
        application is in production
  -pusherApp string
        pusher app id (default "9")
  -pusherHost string
        pusher host
  -pusherKey string
        pusher key
  -pusherPort string
        pusher port (default "4001")
  -pusherSecret string
        pusher secret
   -pusherSecure
        pusher server uses SSL (true or false)
~~~~

