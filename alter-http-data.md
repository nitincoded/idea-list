#Altering HTTP Data

Content Adaptation is the right term to describe the modification of HTTP responses.

##Squid

To alter HTTP headers, there are the header_replace, request_header_replace, and reply_header_replace directives. There's also the url_rewrite_program directive and Squirm is the way forward if you don't want to get started from scratch.

For modifying the HTTP body, Squid has ICAP and eCAP.

##Apache

Apache can run content to external applications using the mod_ext_filter module  
http://httpd.apache.org/docs/2.2/mod/mod_ext_filter.html

The mod_substitute module can be used to replace data in the HTTP response body.

There's an example for using Apache's Reverse Proxy with Content Rewrites at  
http://blogs.reliablepenguin.com/2011/02/01/reverse-proxy-with-content-rewrites  
"To solve the problem we setup mod_proxy as a reverse proxy. Then we used mod_headers, mod_filter and mod_substitute to rewrite the javascript going to client and force the use of the youtube alternative."

##Varnish

Varnish started off as a reverse-proxy web accelerator, unlike Squid which was meant to be a client-side proxy and then evolved (or did someone just make that up and post it on the Internet?). Varnish has limited capabilities - no POST caching (?), and no HTTPS (?).  
TODO: Investigate content adaptation with Nginx.

##Nginx

Nginx can do some pretty cool stuff such as caching POST responses (except in certain cases such as multi-block POST responses?).  
TODO: Investigate content adaptation with Nginx.
