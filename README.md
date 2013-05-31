RecentChanges
=============

An alternative to ActivityStreams for representing updates to a site inspired by wiki style RecentChanges.

Original post: http://sandeep.shetty.in/2013/05/recentchanges-alternative-to.html

* Every resource (URL) has a RecentChanges endpoint.
* The RecentChanges endpoint at each level of the (URL) hierarchy aggregates all RecentChanges under it.
  * The RecentChanges endpoint of the site aggregates site-wide RecentChanges.
* RecentChanges only requires/uses 4 verbs: Post, Respond, Update, Delete (open to renaming these but the idea is that 4 verbs are enough)
* Examples:
  * Sandeep Shetty posted Foobar. (new post)
  * Sandeep Shetty updated Foobar. (edited an existing post)
  * AnonymousOnPurpose responded to Foobar. (commented on a post - could even be a response to a specific comment)
  * Sandeep Shetty deleted Foobar. (deleted a post)
