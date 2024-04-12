# Workflow
1. Input target(s)
2. Find subdomains -> Amass, FFUF basic WL
3. Find APIs -> FFUF kite WL
4. Find directories -> gau, FFUF recursive basic WL
5. Use found URLs to create custom target WL
	1. Get all URLs
	2. Use unfurl to get domains, paths and keys
	3. Combine into target WL
6. Get HTML and JS files for URLs
7. Use *** to compare and get specific unique words
8. add to custom WL
9. Repeat steps 2-4 with custom WL
11. Scan with httpx to check if they are alive
12. Scan with nuclei for low fruit vulnerabilities

# Output files
- Absolutely all URLs found
- Alive URLs
- Custom targer worldlist

# Components
- Content discovery
- Custom WL creator
- Scanner

# Options
-w [subdomain wordlist] [API wordlist] [directories wordlist] -> Default is seclists/***, kiterunner large, seclists/***
-s [1-3] -> Perform scanning 1=httpx 2=nuclei 3=both
-f s/a/d -> Find subdomains, APIs, directories, or a combination of the 3 (s, a, d, sa, sd, ad)

# Notes
- TBD if default wordlists should be on /usr/share/(seclists/* - kiterunner) or ./DefaultWordlists
