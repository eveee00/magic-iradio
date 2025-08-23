# magic-iradio

## Credits
I know that some similar projects exist and I will credit them here.
1. [edberoi/python-airmusicapi](https://github.com/edberoi/python-airmusicapi)
   - Nice python API, well documented XML.
2. [kayrus/iradio](https://github.com/kayrus/iradio)
   - General info about the firmware inside
3. [RobinMeis/AirMusic](https://github.com/RobinMeis/AirMusic/tree/master/docs)
   - Even more documentation about the "XML API"
4. [hsiboy's gist](https://gist.github.com/hsiboy/5662ee465979550452cf0470ff144353)
   - Info about the hardware
  
## My device
I have a Tschibo "TCM" Internetradio. I don't have the exact model though, since it isn't listed on the device itself. [This](https://www.tchibo.de/products/112837416270/wlan-internetradio-mit-farbdisplay?article_id=120642108004) one appears to be the closest one to mine (newer model?).

*Will add pictures later*

## Shell access
*Will be expanded later*

Both SSH and Telnet seem to not be present on my device.

## Ports
### 80
  - Identifies itself as "magic iradio"
  - Runs the API to control the device through the app. API uses [basic auth](https://github.com/edberoi/python-airmusicapi?tab=readme-ov-file#authentication) and the password should be the same on every device.
  - Apparently, on some olderr models, [no auth was required](https://github.com/edberoi/python-airmusicapi?tab=readme-ov-file#authentication) to use the API. This isn't the case for my device though.

### 8080
  - Uses the same authentication as port 80
  - No function currently known
  - cURL errors out:
    
    ```
    $ curl -H 'Authorization: Basic c3UzZzRnbzZzazc6amkzOTQ1NHh1L14=' http://192.168.178.95:8080
    curl: (1) Received HTTP/0.9 when not allowed
    ```
  - You can actually view this in the browser, though it will error out:

    ```
    can't open 'index.html'
    HTTP/1.0 404 Not Found
    Content-type: text/html
    Date: Sat, 23 Aug 2025 00:04:51 GMT
    Connection: close

    <HTML><HEAD><TITLE>404 Not Found</TITLE></HEAD>
    <BODY><H1>404 Not Found</H1>
    The requested URL was not found
    </BODY></HTML>
    ```
    
