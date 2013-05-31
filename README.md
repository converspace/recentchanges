# RecentChanges

A simple alternative to ActivityStreams for representing updates to a site inspired by wiki style RecentChanges.

Original post: http://sandeep.shetty.in/2013/05/recentchanges-alternative-to.html

* Every resource (URL) has a RecentChanges endpoint.
* The RecentChanges endpoint at each level of the (URL) hierarchy aggregates all RecentChanges under it.
  * The RecentChanges endpoint of the site aggregates site-wide RecentChanges.
* RecentChanges only requires/uses 4 verbs: Post, Respond, Update, Delete. (open to renaming these but the idea is that 4 verbs are enough)
* Examples:
 * New Post: `Sandeep Shetty posted [Foobar](http://example.com/foobar)`
 * Edited an existing post: `Sandeep Shetty updated [Foobar](http://example.com/foobar) with [http://example.com/diff/v1-vs-v2]`
 * Comment on a post: `AnonymousOnPurpose responded to [Foobar](http://example.com/foobar) with "[Hello world! ...](http://example.com/comment/22)"`
 * Respond to a specific comment: `AnonymousOnPurpose responded to [Hello world! ...](http://example.com/comment/22) with "[Hello world again! ...](http://example.com/comment/222)"`
 * `likes` are just a [canned response](http://sandeep.shetty.in/2012/10/facebooks-like-is-just-canned-response.html) that could be represented by something like emoji: `AnonymousOnPurpose responded to [Foobar](http://example.com/foobar) with "[:like:](http://example.com/comment/2222)"`
 * Deleted a post: `Sandeep Shetty deleted [Foobar](http://example.com/foobar)`


### References
* Mandatory link to xkcd: http://xkcd.com/927/
* http://c2.com/cgi/wiki?RecentChanges
* http://c2.com/cgi/wiki?RecentChangesDiscussion
