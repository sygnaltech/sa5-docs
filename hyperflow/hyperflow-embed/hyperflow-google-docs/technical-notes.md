# Technical Notes

## Library Positioning

* Combine into `hf-embed`
  * Add handlers for embedding
  * Config options
* Merge into `hf-page` as a module option&#x20;

## Config

### Legacy notes

{% code overflow="wrap" %}
```html
<script type="hyperflow/google-doc">
{
  "type": "gdoc",
  "version": "1",
  "src": "https://docs.google.com/document/d/1_t3yiiYHYM6Q5mGbb2piDq3QedOCo3XC12QhHnmd7q8/edit",
  "theme": "default"
}
</script>
```
{% endcode %}



## Example CSS

Example doc `<style>` before fixup.&#x20;

{% code overflow="wrap" %}
```css
@import url(https://themes.googleusercontent.com/fonts/css?kit=wAPX1HepqA24RkYW1AuHYA);
ul.lst-kix_list_1-0{
    list-style-type:none
}
.lst-kix_dkb9mlmxhukn-0>li:before{
    content:"\0025cf "
}
.lst-kix_dkb9mlmxhukn-1>li:before{
    content:"\0025cb "
}
.lst-kix_dkb9mlmxhukn-2>li:before{
    content:"\0025a0 "
}
ul.lst-kix_list_1-3{
    list-style-type:none
}
.lst-kix_list_1-0>li:before{
    content:"\0025cf "
}
ul.lst-kix_list_1-4{
    list-style-type:none
}
ul.lst-kix_list_1-1{
    list-style-type:none
}
ul.lst-kix_list_1-2{
    list-style-type:none
}
ul.lst-kix_list_1-7{
    list-style-type:none
}
.lst-kix_list_1-1>li:before{
    content:"\0025cb "
}
.lst-kix_list_1-2>li:before{
    content:"\0025a0 "
}
ul.lst-kix_list_1-8{
    list-style-type:none
}
ul.lst-kix_list_1-5{
    list-style-type:none
}
ul.lst-kix_list_1-6{
    list-style-type:none
}
.lst-kix_dkb9mlmxhukn-7>li:before{
    content:"\0025cb "
}
ul.lst-kix_dkb9mlmxhukn-7{
    list-style-type:none
}
ul.lst-kix_dkb9mlmxhukn-8{
    list-style-type:none
}
.lst-kix_list_1-3>li:before{
    content:"\0025cf "
}
.lst-kix_list_1-4>li:before{
    content:"\0025cb "
}
ul.lst-kix_dkb9mlmxhukn-5{
    list-style-type:none
}
.lst-kix_dkb9mlmxhukn-6>li:before{
    content:"\0025cf "
}
.lst-kix_dkb9mlmxhukn-8>li:before{
    content:"\0025a0 "
}
ul.lst-kix_dkb9mlmxhukn-6{
    list-style-type:none
}
ul.lst-kix_dkb9mlmxhukn-3{
    list-style-type:none
}
.lst-kix_dkb9mlmxhukn-5>li:before{
    content:"\0025a0 "
}
ul.lst-kix_dkb9mlmxhukn-4{
    list-style-type:none
}
ul.lst-kix_dkb9mlmxhukn-1{
    list-style-type:none
}
ul.lst-kix_dkb9mlmxhukn-2{
    list-style-type:none
}
ul.lst-kix_dkb9mlmxhukn-0{
    list-style-type:none
}
.lst-kix_dkb9mlmxhukn-3>li:before{
    content:"\0025cf "
}
.lst-kix_list_1-7>li:before{
    content:"\0025cb "
}
.lst-kix_dkb9mlmxhukn-4>li:before{
    content:"\0025cb "
}
.lst-kix_list_1-5>li:before{
    content:"\0025a0 "
}
.lst-kix_list_1-6>li:before{
    content:"\0025cf "
}
li.li-bullet-0:before{
    margin-left:-18pt;
    white-space:nowrap;
    display:inline-block;
    min-width:18pt
}
.lst-kix_list_1-8>li:before{
    content:"\0025a0 "
}
ol{
    margin:0;
    padding:0
}
table td,table th{
    padding:0
}
.c13{
    -webkit-text-decoration-skip:none;
    color:#43474b;
    font-weight:400;
    text-decoration:underline;
    vertical-align:baseline;
    text-decoration-skip-ink:none;
    font-size:22pt;
    font-family:"Arial";
    font-style:normal
}
.c16{
    margin-left:36pt;
    padding-top:0pt;
    padding-left:0pt;
    padding-bottom:10pt;
    line-height:1.15;
    orphans:2;
    widows:2;
    text-align:left
}
.c10{
    padding-top:20pt;
    padding-bottom:8pt;
    line-height:1.0791666666666666;
    page-break-after:avoid;
    orphans:2;
    widows:2;
    text-align:center
}
.c7{
    color:#43474b;
    font-weight:700;
    text-decoration:none;
    vertical-align:baseline;
    font-size:13pt;
    font-family:"Arial";
    font-style:normal
}
.c23{
    color:#43474b;
    font-weight:400;
    text-decoration:none;
    vertical-align:baseline;
    font-size:13.5pt;
    font-family:"Calibri";
    font-style:normal
}
.c1{
    color:#43474b;
    font-weight:400;
    text-decoration:none;
    vertical-align:baseline;
    font-size:13.5pt;
    font-family:"Arial";
    font-style:normal
}
.c12{
    color:#43474b;
    font-weight:400;
    text-decoration:none;
    vertical-align:baseline;
    font-size:9.5pt;
    font-family:"Arial";
    font-style:normal
}
.c2{
    color:#43474b;
    font-weight:400;
    text-decoration:none;
    vertical-align:baseline;
    font-size:10pt;
    font-family:"Calibri";
    font-style:normal
}
.c4{
    color:#43474b;
    font-weight:700;
    text-decoration:none;
    vertical-align:baseline;
    font-size:13.5pt;
    font-family:"Arial";
    font-style:normal
}
.c18{
    color:#084c7f;
    font-weight:700;
    text-decoration:none;
    vertical-align:baseline;
    font-size:18pt;
    font-family:"Arial";
    font-style:normal
}
.c19{
    color:#43474b;
    font-weight:400;
    text-decoration:none;
    vertical-align:baseline;
    font-size:10.5pt;
    font-family:"Arial";
    font-style:normal
}
.c9{
    color:#43474b;
    font-weight:400;
    text-decoration:none;
    vertical-align:baseline;
    font-size:11.5pt;
    font-family:"Arial"
}
.c0{
    padding-top:0pt;
    padding-bottom:10pt;
    line-height:1.7708333333333333;
    orphans:2;
    widows:2;
    text-align:center
}
.c3{
    padding-top:0pt;
    padding-bottom:10pt;
    line-height:1.15;
    orphans:2;
    widows:2;
    text-align:center
}
.c8{
    padding-top:23pt;
    padding-bottom:0pt;
    line-height:1.2208333333333334;
    orphans:2;
    widows:2;
    text-align:center
}
.c20{
    padding-top:23pt;
    padding-bottom:10pt;
    line-height:1.2208333333333334;
    orphans:2;
    widows:2;
    text-align:center
}
.c11{
    padding-top:0pt;
    padding-bottom:8pt;
    line-height:1.0791666666666666;
    orphans:2;
    widows:2;
    text-align:center
}
.c14{
    padding-top:0pt;
    padding-bottom:10pt;
    line-height:1.0;
    orphans:2;
    widows:2;
    text-align:center
}
.c27{
    font-weight:400;
    text-decoration:none;
    vertical-align:baseline;
    font-family:"Arial"
}
.c26{
    font-size:10pt;
    font-family:"Calibri";
    font-weight:400
}
.c28{
    text-decoration-skip-ink:none;
    -webkit-text-decoration-skip:none;
    text-decoration:underline
}
.c29{
    background-color:#ffffff;
    max-width:540pt;
    padding:36pt 36pt 36pt 36pt
}
.c25{
    padding:0;
    margin:0
}
.c24{
    color:#43474b;
    font-size:13.5pt
}
.c15{
    font-size:11.5pt;
    font-weight:700
}
.c22{
    page-break-after:avoid
}
.c30{
    font-weight:700
}
.c17{
    font-size:11.5pt
}
.c6{
    height:13.5pt
}
.c5{
    font-style:italic
}
.c21{
    font-size:9.5pt
}
.title{
    padding-top:0pt;
    -webkit-text-decoration-skip:none;
    color:#43474b;
    text-decoration:underline;
    font-size:26pt;
    padding-bottom:2pt;
    line-height:1.0791666666666666;
    page-break-after:avoid;
    background-color:#ffffff;
    text-decoration-skip-ink:none;
    border-bottom-width:0pt;
    font-family:"Arial";
    border-bottom-style:solid;
    orphans:2;
    widows:2;
    text-align:center
}
.subtitle{
    padding-top:0pt;
    color:#666666;
    font-size:15pt;
    padding-bottom:16pt;
    font-family:"Arial";
    line-height:1.15;
    page-break-after:avoid;
    orphans:2;
    widows:2;
    text-align:center
}
li{
    color:#43474b;
    font-size:13.5pt;
    font-family:"Arial"
}
p{
    margin:0;
    color:#43474b;
    font-size:13.5pt;
    font-family:"Arial"
}
h1{
    padding-top:20pt;
    color:#084c7f;
    font-weight:700;
    font-size:18pt;
    padding-bottom:8pt;
    font-family:"Arial";
    line-height:1.0791666666666666;
    page-break-after:avoid;
    orphans:2;
    widows:2;
    text-align:center
}
h2{
    padding-top:23pt;
    color:#43474b;
    font-weight:700;
    font-size:13.5pt;
    padding-bottom:10pt;
    font-family:"Arial";
    line-height:1.2208333333333334;
    page-break-after:avoid;
    orphans:2;
    widows:2;
    text-align:center
}
h3{
    padding-top:16pt;
    color:#434343;
    font-size:14pt;
    padding-bottom:4pt;
    font-family:"Arial";
    line-height:1.15;
    page-break-after:avoid;
    orphans:2;
    widows:2;
    text-align:center
}
h4{
    padding-top:14pt;
    color:#666666;
    font-size:12pt;
    padding-bottom:4pt;
    font-family:"Arial";
    line-height:1.15;
    page-break-after:avoid;
    orphans:2;
    widows:2;
    text-align:center
}
h5{
    padding-top:12pt;
    color:#666666;
    font-size:13.5pt;
    padding-bottom:4pt;
    font-family:"Arial";
    line-height:1.15;
    page-break-after:avoid;
    orphans:2;
    widows:2;
    text-align:center
}
h6{
    padding-top:12pt;
    color:#666666;
    font-size:13.5pt;
    padding-bottom:4pt;
    font-family:"Arial";
    line-height:1.15;
    page-break-after:avoid;
    font-style:italic;
    orphans:2;
    widows:2;
    text-align:center
}

```
{% endcode %}
