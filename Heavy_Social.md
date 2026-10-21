# Search across the top social networks with one-click instantly from your browser
<br>

<img width="433" src="https://user-images.githubusercontent.com/104733166/196797100-7af0b88b-0158-4716-806d-89947a0b7f6f.png">


### This bookmarklet checks a username across 17 networks (18 tabs):
- X / Twitter (profile + people search)
- Facebook
- Instagram
- Threads
- TikTok
- YouTube
- LinkedIn
- Snapchat
- Telegram
- Reddit
- Pinterest
- VK
- Twitch
- Kick
- Bluesky
- GitHub
- Linktree

<br>

<img width="433" src="https://user-images.githubusercontent.com/104733166/196797572-2ef697e9-2b31-4807-9213-c35f7d53f85b.png">

<br>

**Tips:**
- A leading `@` and spaces are removed automatically (`@john_doe` → `john_doe`).
- Bluesky: `john` is checked as `john.bsky.social`; a full handle like `john.example.com` is used as typed.
- LinkedIn, Facebook and Instagram may ask you to log in before showing a profile.
- **Pop-ups:** browsers only open one tab per click by default. Allow pop-ups for the site you run it from to open everything at once. Otherwise, a panel appears top-right with the blocked sites as clickable links.

Simply copy the JS code below, create a new bookmark, and name it as you wish.
Instructions here: https://github.com/C3n7ral051nt4g3ncy/OSINT-Bookmarklets

```
javascript:!function(){var t=prompt("Heavy Social \u2014 enter a username \ud83d\udc64:","");if(null!==t&&(t=t.trim().replace(/^@+/,"").replace(/\s+/g,""))){var e=encodeURIComponent(t),o=[["X / Twitter","https://x.com/"+e],["X search (people)","https://x.com/search?q="+e+"&f=user"],["Facebook","https://www.facebook.com/"+e],["Instagram","https://www.instagram.com/"+e+"/"],["Threads","https://www.threads.com/@"+e],["TikTok","https://www.tiktok.com/@"+e],["YouTube","https://www.youtube.com/@"+e],["LinkedIn","https://www.linkedin.com/in/"+e+"/"],["Snapchat","https://www.snapchat.com/add/"+e],["Telegram","https://t.me/"+e],["Reddit","https://www.reddit.com/user/"+e+"/"],["Pinterest","https://www.pinterest.com/"+e+"/"],["VK","https://vk.com/"+e],["Twitch","https://www.twitch.tv/"+e],["Kick","https://kick.com/"+e],["Bluesky","https://bsky.app/profile/"+e+(-1===t.indexOf(".")?".bsky.social":"")],["GitHub","https://github.com/"+e],["Linktree","https://linktr.ee/"+e]],n=[];if(o.forEach(function(t){var e=null;try{e=window.open(t[1],"_blank")}catch(t){}if(e)try{e.opener=null}catch(t){}else n.push(t)}),n.length){var a=document.getElementById("hs-host");a&&a.remove(),(a=document.createElement("heavysocial-panel")).id="hs-host";var i={all:"initial",position:"fixed",top:"12px",right:"12px",left:"auto",bottom:"auto","z-index":"2147483647",display:"block",width:"auto",height:"auto",transform:"none"};for(var r in i)a.style.setProperty(r,i[r],"important");var p=a.attachShadow?a.attachShadow({mode:"open"}):a,s=document.createElement("div");s.style.cssText="position:relative;box-sizing:border-box;background:%23111;color:%23eee;font:13px/1.4 system-ui,sans-serif;padding:12px 14px;border:1px solid %23444;border-radius:8px;box-shadow:0 6px 24px rgba(0,0,0,.5);max-height:80vh;overflow:auto;width:260px;text-align:left";var c=document.createElement("div");c.textContent="Heavy Social: @"+t+" \u2014 "+n.length+" tab(s) blocked",c.style.cssText="font-weight:600;margin-bottom:4px;padding-right:18px";var l=document.createElement("div");l.textContent="Click to open, or allow pop-ups for this site.",l.style.cssText="color:%23aaa;font-size:12px;margin-bottom:8px";var d=document.createElement("button");d.textContent="\xd7",d.style.cssText="position:absolute;top:6px;right:8px;background:none;border:0;color:%23aaa;font-size:18px;cursor:pointer",d.onclick=function(){a.remove()},s.appendChild(d),s.appendChild(c),s.appendChild(l),n.forEach(function(t){var e=document.createElement("a");e.href=t[1],e.target="_blank",e.rel="noopener noreferrer",e.textContent=t[0],e.style.cssText="display:block;color:%236cf;padding:3px 0;text-decoration:none",e.onclick=function(){e.style.color="%23777"},s.appendChild(e)}),p.appendChild(s),document.documentElement.appendChild(a)}}}();
```
