---
layout:	post
title:	"Redirect non-www to www and http to https .htaccess"
---
Add code below to `.htaccess` file
{% highlight ruby %}
RewriteEngine On

RewriteCond %{HTTP_HOST} !^www\. [NC]
RewriteRule ^(.*)$ http://www.%{HTTP_HOST}/$1 [R=301,L]

RewriteCond %{HTTPS} off
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
{% endhighlight %} 
