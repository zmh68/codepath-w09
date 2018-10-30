# Project 9 - Honeypot

Time spent: **6** hours spent in total


## Honeypots deployed
In total, 56 honeypots where deployed using 42 virtual machines across 4 hosting providers. The breakdown of honeypot types deployed was:

Count | Honeypot Type
----- | ----------------
20 | Cowrie
11 | Conpot
19 | Dionaea
2 | ElasticHoney
1 | Snort
1 | Suricata
1 | up0f
1 | wordpot

Instances running Conpot, ElasticHoney, and Wordpot had Cowrie added mid-way through data collection (as it was determined they could function together). 

Instances were split across these hosting providers:

Count | Hosting Provider
----- | ----------------
16 | Azure
11 | Digital Ocean
8 | Linode
7 | AWS

and were allocated across these countries:

Count | Country
----- | ----------------
19 | United States
5 | South Korea
3 | France
3 | Germany
2 | Europe (unspecified)
2 | India
2 | Japan
2 | Singapore
2 | United Kingdom
1 | Australia
1 | Brazil
1 | Canada
1 | Ireland

Instances were added over the course of a week, with some operating nearly a full week while others only operating a few days. 


## Issues encountered

There weren't any major issue encountered. I didn't use Google Cloud Platform because I didn't have any free credit available (and my school account did not work). 


## Data summary

There's a lot to analyze within this dataset, but here are some very basic observations:

**Number of Attacks**

A total of 1,153,610 attacks were logged. Broken down by honeypot the attack counts are:

Count | Percentage | Honeypot 
----- | ---------- | --------
998,465 | 86.55% | dionaea
114,720 | 9.94% | cowrie
16,677 | 1.45% | p0f
9,362 | 0.81% | suricata
9,320 | 0.81% | conpot
5,041 | 0.44% | snort
25 | 0% | elastichoney
0 | 0% | wordpot


IP addresses were resolved to associated countries using the [maxmind GeoLite2 database](https://dev.maxmind.com/geoip/geoip2/geolite2/), the countries with the highest number of attacks were:


Count | Percentage | Country 
----- | ---------- | --------
463,914 | 40.21% | United States
96,865 | 8.40% | Estonia
71,651 | 6.21% | Ireland
70,886 | 6.14% | United Kingdom
58,593 | 5.80% | Russia
43,660 | 3.78% | China
37,569 | 3.26% | Vietnam
36,579 | 3.17% | France
36,325 | 3.15% | Ukraine
35,801 | 3.10% | Netherlands
22,643 | 1.96% | India
19,004 | 1.65% | Indonesia
12,850 | 1.11% | Brazil


Since a single IP address could often be the source of many log entries, it is also interesting to examine the number of unique IP addresses per country. The countries with the highest number of unique IP addresses logged were:

Count | Percentage | Country 
----- | ---------- | --------
6,741 | 11.70% | China
6,651 | 11.54% | Vietnam
4,831 | 8.38% | Russia
4,218 | 7.32% | India
4,176 | 7.25% | Indonesia
4,052 | 7.03% | United States
3,455 | 6.00% | Brazil
1,942 | 3.37% | Taiwan
1,490 | 2.59% | Thailand
1,390 | 2.41% | Venezuela
1,193 | 2.07% | Turkey
1,088 | 1.89% | Ukraine
974 | 1.69% | Micronesia 
826 | 1.43% | Egypt
823 | 1.43% | South Korea
732 | 1.27% | Hong Kong
700 | 1.21% | Iran
601 | 1.04% | Philippines


**Malware Samples**

Dionaea captured 8 samples of malware, signatures shown below:

<img src="./dcap.png"/>


## Unresolved questions 
It is unclear why there were no attacks on the wordpot instance. Visiting the instance did show the honeypot Wordpress site, but I did not attempt an attack. It's possible there was a configuration problem. 


## Data Export
The data collected is available in the [data](./data/) directory of this repository. The files included are:

* **instances.csv** - a CSV export detailing the hosting provider and data center location for each honeypot instance deployed.
* **sensors.csv** - a CSV export of the data MHN keeps linking host identifiers to IP addresses.
* **session_2018102901.json.zip** - a zip file of the file exported by mongoexport. (NOTE: zipped file uploaded, as original was ~423 MB)
