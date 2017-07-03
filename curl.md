# cURL

* [How do I download a document from an HTTP server?](#how-do-i-download-a-document-from-an-http-server)
* [How do I download a document from an HTTP server and rename the file?](#how-do-i-download-a-document-from-an-http-server-and-rename-the-file)
* [How do I tell curl to follow redirects?](*how-do-i-tell-curl-to-follow-redirects?)
* [How do I make HTTP requests like GET, POST, PUT, and DELETE?](#how-do-i-make-http-requests-like-get-post-put-and-delete)
* [How do I add data to an HTTP request?](#how-do-i-add-data-to-an-http-request)
* [How do I add data to an HTTP request from a file?](#how-do-i-add-data-to-an-http-request-from-a-file)

## How do I download a document from an HTTP server?
`curl -O http://www.example.com/document`

## How do I download a document from an HTTP server and rename the file?
<tt>curl -o <i>file</i> http://www.example.com/document</tt>

## How do I tell curl to follow redirects?
Use the location flag `-L`:

`curl -L -O http://www.example.com/document`

## How do I make HTTP requests like GET, POST, PUT, and DELETE?
Use the request flag `-X`, for example: 

`curl -X POST http://www.example.com/end-point`

## How do I add data to an HTTP request?
Use the data flag `-d` and the content header, for example:

`curl -X POST -H "Content-Type: application/json" -d '{"key":"val"}' http://www.example.com/end-point`

## How do I add data to an HTTP request from a file?
Place an `@` in front of the filename:

`curl -X POST -H "Content-Type: application/json" -d @jsonfile http://www.example.com/end-point`
