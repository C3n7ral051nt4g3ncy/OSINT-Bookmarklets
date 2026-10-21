# Webpage Dates 📅 — Last Modification & Publication Dates

Click the bookmarklet on any page and a panel lists **every date signal the page exposes**, with a note on how reliable each one is.

### ⚠️ Why the old `document.lastModified` is a trap

`document.lastModified` only reflects the server's `Last-Modified` header. Most modern pages (news sites, social media, anything built by a CMS) are generated on the fly and send no such header, so the browser **returns the current date and time** instead. Reporting that as "last modified" is a classic OSINT error. This bookmarklet flags it automatically.

### What it checks

| Source | What it reveals |
|---|---|
| `document.lastModified` | Server file date — or flagged ⚠ when it's just "now" |
| HTTP `Last-Modified` | File modification date sent by the server (static pages, PDFs, images) |
| HTTP `ETag` / `Age` | Content fingerprint (changes with the file) / how long the copy sat in a CDN cache |
| `<meta article:published_time / modified_time>` | Open Graph dates set by the CMS (news, blogs) |
| `<meta og:updated_time>`, Dublin Core, Parse.ly, Sailthru, citation tags | Other CMS / publisher / academic metadata |
| JSON-LD `datePublished` / `dateModified` / `dateCreated` / `uploadDate` | Schema.org structured data — what Google uses to date a page |
| `<time datetime>` | Dates printed in the page body |
| Wayback Machine / archive.today links | First and later captures — independent dating when the page itself has no reliable date |

The panel also shows the **oldest and newest** dates found. Dates are displayed in UTC.

**Caveat:** every on-page date is set by whoever runs the site and can be edited or back-dated. Corroborate with archive captures.

### Install

Copy/Paste the below into a new Bookmark, give it any title you like, then click it on any page:

```
javascript:!function(){var e=Date.now(),t=[];function a(e,a,n){if(a){var o=new Date(a),i=String(a).trim();isNaN(o)||(i=/^\d{4}-\d{2}-\d{2}$/.test(i)?i+" (date only)":function(e){var t=function(e){return(e<10?"0":"")+e};return e.getUTCFullYear()+"-"+t(e.getUTCMonth()+1)+"-"+t(e.getUTCDate())+" "+t(e.getUTCHours())+":"+t(e.getUTCMinutes())+":"+t(e.getUTCSeconds())+" UTC"}(o)),t.some(function(t){return t[0]===e&&t[1]===i})||t.push([e,i,n||"",isNaN(o)?null:o])}}function n(t){return t&&Math.abs(e-t.getTime())<12e4}var o=new Date(document.lastModified);a("document.lastModified",document.lastModified,n(o)?"\u26a0 = current time: server sent no date, NOT a real modification date":"From the server\u2019s Last-Modified header");var i={"article:published_time":"Published (Open Graph article)","article:modified_time":"Modified (Open Graph article)","og:updated_time":"Updated (Open Graph)",date:"Meta date",pubdate:"Meta pubdate",publishdate:"Meta publishdate","dc.date":"Dublin Core date","dc.date.issued":"Dublin Core issued","dcterms.created":"Dublin Core created","dcterms.modified":"Dublin Core modified","last-modified":"Meta last-modified",revised:"Meta revised","sailthru.date":"Sailthru (news CMS)","parsely-pub-date":"Parse.ly (news CMS)",citation_publication_date:"Academic citation",citation_date:"Academic citation"};Array.prototype.forEach.call(document.querySelectorAll("meta"),function(e){var t=(e.getAttribute("property")||e.getAttribute("name")||e.getAttribute("itemprop")||"").t
