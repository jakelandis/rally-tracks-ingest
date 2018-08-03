
Modifications to the [tool archive](ftp://ita.ee.lbl.gov/software/WorldCup_tools.tar.gz) provided at http://ita.ee.lbl.gov/html/contrib/WorldCup.html 

## recreate.c 
* Modifies the recreate output from the default: 
    * Uses 127.0.0.1 for all client IPs (instead of the of the unique integer)
    * JSON lines instead of log file lines. The format is `{ "message" : "<log line here>}` with one valid JSON per line. 
    
Output example:
```$json
{ "message" : "127.0.0.1 - - [30/Apr/1998:21:30:17 +0000] \"GET /images/hm_bg.jpg HTTP/1.0\" 200 -"}
{ "message" : "127.0.0.1 - - [30/Apr/1998:21:30:53 +0000] \"GET /images/hm_bg.jpg HTTP/1.0\" 200 -"}
{ "message" : "127.0.0.1 - - [30/Apr/1998:21:31:12 +0000] \"GET /images/hm_bg.jpg HTTP/1.0\" 200 -"}
```

Usage download the [tool archive](ftp://ita.ee.lbl.gov/software/WorldCup_tools.tar.gz) and replace recreate.c and follow readme instructions. 

For example:
```bash
make recreate
gzip -dc input/test_log.gz | bin/recreate state/object_mappings.sort > output/recreate.out
```

### License

Original license text:

               Copyright (C) 1997, 1998, 1999 Hewlett-Packard Company
                             ALL RIGHTS RESERVED.
     
      The enclosed software and documentation includes copyrighted works
      of Hewlett-Packard Co. For as long as you comply with the following
      limitations, you are hereby authorized to (i) use, reproduce, and
      modify the software and documentation, and to (ii) distribute the
      software and documentation, including modifications, for
      non-commercial purposes only.
          
      1.  The enclosed software and documentation is made available at no
          charge in order to advance the general development of
          the Internet, the World-Wide Web, and Electronic Commerce.
     
      2.  You may not delete any copyright notices contained in the
          software or documentation. All hard copies, and copies in
          source code or object code form, of the software or
          documentation (including modifications) must contain at least
          one of the copyright notices.
     
      3.  The enclosed software and documentation has not been subjected
          to testing and quality control and is not a Hewlett-Packard Co.
          product. At a future time, Hewlett-Packard Co. may or may not
          offer a version of the software and documentation as a product.
      
      4.  THE SOFTWARE AND DOCUMENTATION IS PROVIDED "AS IS".
          HEWLETT-PACKARD COMPANY DOES NOT WARRANT THAT THE USE,
          REPRODUCTION, MODIFICATION OR DISTRIBUTION OF THE SOFTWARE OR
          DOCUMENTATION WILL NOT INFRINGE A THIRD PARTY'S INTELLECTUAL
          PROPERTY RIGHTS. HP DOES NOT WARRANT THAT THE SOFTWARE OR
          DOCUMENTATION IS ERROR FREE. HP DISCLAIMS ALL WARRANTIES,
          EXPRESS AND IMPLIED, WITH REGARD TO THE SOFTWARE AND THE
          DOCUMENTATION. HP SPECIFICALLY DISCLAIMS ALL WARRANTIES OF
          MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE.
      
      5.  HEWLETT-PACKARD COMPANY WILL NOT IN ANY EVENT BE LIABLE FOR ANY
          DIRECT, INDIRECT, SPECIAL, INCIDENTAL OR CONSEQUENTIAL DAMAGES
          (INCLUDING LOST PROFITS) RELATED TO ANY USE, REPRODUCTION,
          MODIFICATION, OR DISTRIBUTION OF THE SOFTWARE OR DOCUMENTATION.