# RecentChanges

A simple alternative to ActivityStreams for representing updates to a site inspired by wiki style RecentChanges.

Original post: http://sandeep.shetty.in/2013/05/recentchanges-alternative-to.html

* Every resource (URL) SHOULD have a RecentChanges endpoint.

```http
GET /some-resource HTTP/1.1
Host: sandeep.shetty.in
```
```http
HTTP/1.1 200 OK
Link: <http://sandeep.shetty.in/recentchanges-endpoint?res=/some-resource>; rel="http://example.com/TDB"

<html>
...
<link href="http://sandeep.shetty.in/recentchanges-endpoint?res=/some-resource" rel="http://example.com/TDB" />
...
```
* The RecentChanges endpoint at each level of the (URL) hierarchy SHOULD aggregate all RecentChanges under it.
* The RecentChanges endpoint of the site MUST aggregates site-wide RecentChanges.

```http
GET / HTTP/1.1
Host: sandeep.shetty.in
```
```http
HTTP/1.1 200 OK
Link: <http://sandeep.shetty.in/recentchanges-endpoint>; rel="http://example.com/TDB"

<html>
...
<link href="http://sandeep.shetty.in/recentchanges-endpoint" rel="http://example.com/TDB" />
...
```
* The RecentChanges endpoint could return HTML (marked up with microformats) or JSON.
* RecentChanges only requires/uses 4 verbs: Post, Update, Respond, Delete (PURD). (open to renaming these but **the key idea is that we only need a limited number of verbs**: 4 based on use cases below)
* Use-cases:
 * New Post: <pre>[Sandeep Shetty](http://sandeep.shetty.in/) posted [Foobar](http://example.com/foobar)</pre>
 * Edit an existing post: 
<pre>[Sandeep Shetty](http://sandeep.shetty.in/) updated [Foobar](http://example.com/foobar) with http://example.com/diff/v1-vs-v2 </pre>
 * Comment on a post: <pre>[Barnaby Walters](http://waterpigs.co.uk/) responded to [Foobar](http://example.com/foobar) with "[Hello world! ...](http://example.com/comment/22)"</pre>
 * Response to a specific comment: <pre>[Barnaby Walters](http://waterpigs.co.uk/) responded to "[Hello world! ...](http://example.com/comment/22)" with "[Hello world again! ...](http://example.com/comment/222)"</pre>
 * `likes` are just a [canned response](http://sandeep.shetty.in/2012/10/facebooks-like-is-just-canned-response.html) that could be represented by something like emoji: <pre>[Sandeep Shetty](http://sandeep.shetty.in/) responded to "[Hello world again! ...](http://example.com/comment/222)" with "[:like:](http://example.com/comment/2222)"</pre>
 * Delete post: <pre>[Sandeep Shetty](http://sandeep.shetty.in/) deleted [Foobar](http://example.com/foobar)</pre>


## TODO
* microformats for marking up RecentChanges.
* JSON format for RecentChanges (could just go with the microformats and skip this - DRY)


## References
* Mandatory link to xkcd: http://xkcd.com/927/
* http://c2.com/cgi/wiki?RecentChanges
* http://c2.com/cgi/wiki?RecentChangesDiscussion
