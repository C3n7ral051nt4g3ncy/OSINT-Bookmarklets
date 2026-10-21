---
### The Powerful Search Bookmarklet will help you search simultaneously the following websites:

- google.com 🇺🇸
- bing.com 🇺🇸
- duckduckgo.com 🇺🇸
- search.brave.com 🇺🇸
- mojeek.com 🇬🇧
- qwant.com 🇫🇷
- yandex.com 🇷🇺
- baidu.com 🇨🇳
- sogou.com 🇨🇳
- so.com (360 Search) 🇨🇳
- search.naver.com 🇰🇷
- search.daum.net 🇰🇷
- search.seznam.cz 🇨🇿
- ahmia.fi 🇫🇮 (Dark Web Search)

**Search tips:**
- `john doe` → searched as the exact phrase `"john doe"`
- `"john" "doe"` → your own quotes are kept as typed
- `~john site:example.com` → a leading `~` sends the query raw (for operators)

**Ahmia:** direct search links no longer work on Ahmia, so the bookmarklet opens the Ahmia homepage and copies your query to the clipboard. Just paste (Ctrl/Cmd + V) and press Enter.

**Pop-ups:** browsers only open one tab per click by default. Allow pop-ups for the site you run it from to open all engines at once. Otherwise, a small panel appears top-right with the blocked engines as clickable links.

Just Copy/paste the below code into your Bookmarks: (instructions + set up are on the .readme file)

```
javascript:!function(){if(/(^|\.)ahmia\.fi$/.test(location.hostname)){var e="";if(0===window.name.indexOf("PS:")&&(e=window.name.slice(3),window.name=""),e||(e=(prompt("Ahmia search:","")||"").trim()),!e)return;var t=document.querySelector('input[name="q"]');return t&&t.form?(t.value=e,void(t.form.requestSubmit?t.form.requestSubmit():t.form.submit())):void alert("PowerSearch: Ahmia search box not found.")}var o=prompt("PowerSearch \u2014 exact phrase (prefix ~ for raw query):","");if(null!==o&&(o=o.trim())){var r;r="~"===o.charAt(0)?o.slice(1).trim():-1!==o.indexOf('"')?o:'"'+o+'"';var a=encodeURIComponent(r);!function(e){try{if(navigator.clipboard&&window.isSecureContext)return void navigator.clipboard.writeText(e).catch(function(){h(e)})}catch(e){}h(e)}(r);var n=[["Google","https://www.google.com/search?q="],["Bing","https://www.bing.com/search?q="],["DuckDuckGo","https://duckduckgo.com/?q="],["Brave","https://search.brave.com/search?q="],["Mojeek","https://www.mojeek.com/search?q="],["Qwant","https://www.qwant.com/?q="],["Yandex","https://yandex.com/search/?text="],["Baidu","https://www.baidu.com/s?wd="],["Sogou","https://www.sogou.com/web?query="],["360 Search","https://www.so.com/s?q="],["Naver","https://search.naver.com/search.naver?query="],["Daum","https://search.daum.net/search?q="],["Seznam","https://search.seznam.cz/?q="]].map(function(e){return[e[0],e[1]+a]});n.push(["Ahmia (dark web) \u2014 click PowerSearch there","https://ahmia.fi/","PS:"+r]);var c=[];if(n.forEach(function(e){var t=null;try{t=window.open(e[1],e[2]||"_blank")}catch(e){}if(t)try{t.opener=null}catch(e){}else c.push(e)}),c.length){var i=document.getElementById("ps-panel");i&&i.remove();var s=document.createElement("div");s.id="ps-panel",s.style.cssText="position:fixed;top:12px;right:12px;z-index:2147483647;background:%23111;color:%23eee;font:13px/1.4 system-ui,sans-serif;padding:12px 14px;border:1px solid %23444;border-radius:8px;box-shadow:0 6px 24px rgba(0,0,0,.5);max-height:80vh;overflow:auto;width:260px";var p=document.createElement("div");p.textContent="PowerSearch: "+c.length+" tab(s) blocked",p.style.cssText="font-weight:600;margin-bottom:4px";var d=document.createElement("div");d.textContent="Click to open, or allow pop-ups for this site.",d.style.cssText="color:%23aaa;font-size:12px;margin-bottom:8px";var m=document.createElement("button");m.textContent="\xd7",m.style.cssText="position:absolute;top:6px;right:8px;background:none;border:0;color:%23aaa;font-size:18px;cursor:pointer",m.onclick=function(){s.remove()},s.appendChild(m),s.appendChild(p),s.appendChild(d),c.forEach(function(e){var t=document.createElement("a");t.href=e[1],t.target=e[2]||"_blank",t.rel="noopener noreferrer",t.textContent=e[0],t.style.cssText="display:block;color:%236cf;padding:3px 0;text-decoration:none",t.onclick=function(){t.style.color="%23777"},s.appendChild(t)}),document.body.appendChild(s)}}function h(e){try{var t=document.createElement("textarea");t.value=e,t.style.cssText="position:fixed;top:-1000px;opacity:0",document.body.appendChild(t),t.select(),document.execCommand("copy"),t.remove()}catch(e){}}}();

```
