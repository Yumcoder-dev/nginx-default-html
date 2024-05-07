# nginx-default-html

Including server information in HTTP response headers can pose security risks. Hackers can exploit known vulnerabilities in specific server versions to launch attacks. For this reason, it's generally recommended to minimize the amount of information disclosed in HTTP response headers, especially regarding server software versions.

To mitigate these risks, you can configure your web server (such as NGINX) to omit the server version information from the response headers. This can be done by adjusting the server configuration. For NGINX, you can achieve this by adding or modifying directives in your NGINX configuration file.

Here's an example of how you can configure NGINX to hide the server version information:

```
 server {
        listen       80;
        server_name  localhost;
        # hive version
        server_tokens off;
        more_set_headers 'Server: your_server_name';
       
        access_log  logs/host.access.log  main;

        location / {
            # ...
        }
        # ...
 }
```