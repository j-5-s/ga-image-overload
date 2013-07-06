# Image Overload For Access to utm.gif
__Warning, highly experimental__.
The purpose of this code is to overload the Native JS `Image` functino
to store a reference to images created with it in order to access them
later. The primary use case is Google Analytics. When the ___utm.gif 
loads we may want to access the parameters sent to Google.

## JSON Object with UTM Vars:

Grabs the image src of the `__utm.gif` that gets sent to GA like:

```text
http://www.google-analytics.com/__utm.gif?utmwv=5.4.3&utms=8&utmn=1087665281&utmhn=localhost&utmcs=UTF-8&utmsr=1280x800&utmvp=398x679&utmsc=24-bit&utmul=en-us&utmje=1&utmfl=11.7%20r700&utmdt=Image%20Override&utmhid=991863851&utmr=-&utmp=%2Findex.html&utmht=1373130295954&utmac=UA-19811292-1&utmcc=__utma%3D1.404091564.1373129891.1373129891.1373129891.1%3B%2B__utmz%3D1.1373129891.1.1.utmcsr%3D(direct)%7Cutmccn%3D(direct)%7Cutmcmd%3D(none)%3B&utmu=qB~
```

and turns it into a JSON object like so:

```Javascript
{
    utmac: "UA-19811292-1",
    utmcc: "__utma%3D1.404091564.1373129891.1373129891.1373129891.1%3B%2B__utmz%3D1.1373129891.1.1.utmcsr%3D(direct)%7Cutmccn%3D(direct)%7Cutmcmd%3D(none)%3B",
    utmcs: "UTF-8",
    utmdt: "Image%20Override",
    utmfl: "11.7%20r700",
    utmhid: "846947542",
    utmhn: "localhost",
    utmht: "1373130612405",
    utmje: "1",
    utmn: "342518970",
    utmp: "%2Findex.html",
    utmr: "-",
    utms: "9",
    utmsc: "24-bit",
    utmsr: "1280x800",
    utmu: "qB~",
    utmul: "en-us",
    utmvp: "398x679",
    utmwv: "5.4.3",
}
```

## License

(The MIT License)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.