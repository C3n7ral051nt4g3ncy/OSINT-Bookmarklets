
---
### The Powerful Search Bookmarklet will help you search simultaneously the following websites:

- google.com 🇺🇸
- duckduckgo.com 🇺🇸
- yandex.com 🇷🇺
- Baidu 🇨🇳
- qwant.com 🇫🇷
- bing.com 🇺🇸
- ahmia.fi 🇫🇮 (Dark Web Search) 

Just Copy/paste the below code into your Bookmarks: (instructions + set up are on the .readme file)
```
javascript:(function()%7Bvar request%3Dprompt("Enter your request%3A ")%3Bvar googlesearch%3D"https%3A%2F%2Fwww.google.com%2Fsearch%3Fq%3D%2522"%2Brequest%2B"%2522"%3Bwindow.open(googlesearch%2C " _blank")%3Bvar duckduckgosearch%3D"https%3A%2F%2Fduckduckgo.com%2F%3Fq%3D%2522"%2Brequest%2B"%2522"%3Bwindow.open(duckduckgosearch%2C "_blank")%3Bvar yandexsearch%3D"https%3A%2F%2Fyandex.com%2F%3Fq%3D%2522"%2Brequest%2B"%2522"%3Bwindow.open(yandexsearch%2C "_blank")%3Bvar qwantsearch%3D"https%3A%2F%2Fqwant.com%2F%3Fq%3D%2522"%2Brequest%2B"%2522"%3Bwindow.open(qwantsearch%2C "_blank")%3Bvar bingsearch%3D"https%3A%2F%2Fwww.bing.com%2Fsearch%3Fq%3D%2522"%2Brequest%2B"%2522"%3Bwindow.open(bingsearch%2C "_blank")%3Bvar ahmia%3D"https%3A%2F%2Fahmia.fi%2Fsearch%2F%3Fq%3D%2522"%2Brequest%2B"%2522"%3Bwindow.open(ahmia%2C "_blank")%3Bvar baidusearch%3D"https%3A%2F%2Fwww.baidu.com%2Fs%3Fq%3Dbaidu%26wd%3D%2522"%2Brequest%2B"%2522"%3Bwindow.open(baidusearch%2C " _blank")%7D)()
```
