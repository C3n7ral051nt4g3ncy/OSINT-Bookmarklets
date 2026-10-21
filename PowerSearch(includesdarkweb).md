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
javascript:!function(){var e=prompt("PowerSearch \u2014 exact phrase (prefix ~ for raw query):","");if(null!==e&&(e=e.trim())){var t;t="~"===e.charAt(0)?e.slice(1).trim():-1!==e.indexOf('"')?e:'"'+e+'"';var o=encodeURIComponent(t);!function(e){try{if(navigator.clipboard&&window.isSecureContext)return void navigator.clipboard.writeText(e).catch(function(){d(e)})}catch(e){}d(e)}(t);var a=[["Google","https://www.google.com/search?q="],["Bing","https://www.bing.com/search?q="],["DuckDuckGo","https://duckduckgo.com/?q="],["Brave","https://search.brave.com/search?q="],["Mojeek","https://www.mojeek.com/search?q="],["Qwant","https://www.qwant.com/?q="],["Yandex","https://yandex.com/search/?text="],["Baidu","https://www.baidu.com/s?wd="],["Sogou","https://www.sogou.com/web?query="],["360 Search","https://www.so.com/s?q="],["Naver","https://search.naver.com/search.naver?query="],["Daum","https://search.daum.net/search?q="],["Seznam","https://search.seznam.cz/?q="]].map(function(e){return[e[0],e[1]+o]});a.push(["Ahmia (dark web) \u2014 paste query","https://ahmia.fi/"]);var n=[];if(a.forEach(function(e){var t=null;try{t=window.open(e[1],"_blank")}catch(e){}if(t)try{t.opener=null}catch(e){}else n.push(e)}),n.length){var r=document.getElementById("ps-panel");r&&r.remove();var c=document.createElement("div");c.id="ps-panel",c.style.cssText="position:fixed;top:12px;right:12px;z-index:2147483647;background:%23111;color:%23eee;font:13px/1.4 system-ui,sans-serif;padding:12px 14px;border:1px solid %23444;border-radius:8px;box-shadow:0 6px 24px rgba(0,0,0,.5);max-height:80vh;overflow:auto;width:260px";var s=document.createElement("div");s.textContent="PowerSearch: "+n.length+" tab(s) blocked",s.style.cssText="font-weight:600;margin-bottom:4px";var p=document.createElement("div");p.textContent="Click to open, or allow pop-ups for this site.",p.style.cssText="color:%23aaa;font-size:12px;margin-bottom:8px";var i=document.createElement("button");i.textContent="\xd7",i.style.cssText="position:absolute;top:6px;right:8px;background:none;border:0;color:%23aaa;font-size:18px;cursor:pointer",i.onclick=function(){c.remove()},c.appendChild(i),c.appendChild(s),c.appendChild(p),n.forEach(function(e){var t=document.createElement("a");t.href=e[1],t.target="_blank",t.rel="noopener noreferrer",t.textContent=e[0],t.style.cssText="display:block;color:%236cf;padding:3px 0;text-decoration:none",t.onclick=function(){t.style.color="%23777"},c.appendChild(t)}),document.body.appendChild(c)}}function d(e){try{var t=document.createElement("textarea");t.value=e,t.style.cssText="position:fixed;top:-1000px;opacity:0",document.body.appendChild(t),t.select(),document.execCommand("copy"),t.remove()}catch(e){}}}();
```
