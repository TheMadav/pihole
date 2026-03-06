# BaFin Warning Domains – Pi-hole Blocklist

## Overview

This repository provides a machine-generated domain blocklist derived from public warning notices published by the German Federal Financial Supervisory Authority (BaFin).

The primary purpose of this list is to allow DNS-based blocking (e.g., via Pi-hole) of domains that BaFin has warned about in connection with unauthorized financial services or suspected fraudulent activity.

The repository contains no application code. It only hosts a regularly updated text file with domains.

## Source

Domains are extracted automatically from the official BaFin RSS feed for consumer warnings:

**[BaFin RSS-Feed](https://www.bafin.de/DE/Service/TopNavigation/RSS/_function/rssnewsfeed.xml)**

Only domains explicitly mentioned in BaFin warning publications are included.

## How It Works

- An automated workflow periodically retrieves the BaFin RSS feed.
- Newly published warning articles are parsed.
- Domains mentioned in the articles are extracted and normalized.
- The resulting deduplicated domain list is written to a plain text file in this repository.
- The list is updated automatically.

Format:

- One domain per line
- No subpath filtering (DNS-level blocking only)
- Intended for direct consumption by DNS filtering systems such as Pi-hole

## Usage [(Pi-hole)](https://pi-hole.net):

1.	Add the raw .txt file URL as a new adlist in Pi-hole.
2.	Update gravity.
3.	Pi-hole will periodically refresh the list according to its configured update schedule.

Note:
DNS-level blocking operates at the domain level. If BaFin warns only about specific subpages of an otherwise legitimate domain, blocking may affect the entire domain.

## Disclaimer

This blocklist is automatically generated from publicly available BaFin RSS data.

- No guarantee is given regarding completeness, correctness, or timeliness.
- Parsing errors or feed changes may lead to missing or incorrectly extracted domains.
- This repository is not affiliated with or endorsed by BaFin.
- Use at your own risk.

For authoritative and legally binding information, refer directly to official BaFin publications.

## License

This repository contains automatically generated data derived from public information.
You may use the domain list at your own discretion.
