# Porter Airlines (porter-airlines)

Porter Airlines is a Canadian carrier headquartered in Toronto, operating as Porter Airlines (Canada) Limited and Porter Airlines Inc. under IATA designator PD, IATA ticketing plate 451, and ICAO code POE. It is the challenger to the Air Canada / WestJet duopoly in Canada, flying an Embraer E195-E2 and De Havilland Dash 8 fleet across domestic, transborder and sun destinations, and it joined IATA as a member in 2026 following IOSA certification. Porter sits in the distribution chain as a conventional GDS-intermediated carrier: agencies reach its inventory through the GDSs (Sabre is named explicitly in Porter's agency terms, and Travelport is the channel Duffel uses to resell Porter content) or through Porter's own ticketless Travel Agency Portal on flyporter.com. Porter's API posture is honestly stated as none-published. There is no developer portal, no public or partner API documentation, no OpenAPI, and no NDC endpoint of any kind.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/porter-airlines/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/porter-airlines/refs/heads/main/apis.yml)

## Tags

- Travel
- Canada
- Aviation
- Airline
- Flights
- Distribution
- GDS
- Booking
- Travel Agents
- Loyalty

## Timestamps

- **Created:** 2026-07-28
- **Modified:** 2026-07-28

## APIs

None. Porter Airlines publishes no public or partner API.

The `developer.`, `developers.`, `apis.` and `corporate.` subdomains do not resolve. `api.flyporter.com` resolves to 34.225.119.133 / 54.157.223.200 but does not answer on port 80 or 443. `docs.flyporter.com` is a Google Workspace CNAME that redirects to an internal Google Drive. Every well-known specification path — `/openapi.json`, `/swagger.json`, `/api-docs`, `/api`, `/apis`, `/developer`, `/developers`, `/docs`, `/.well-known/security.txt`, `/.well-known/ai-plugin.json`, `/llms.txt` — returns 404. The `en-ca` sitemap holds 93 URLs and not one of them is a developer or documentation page. The whole site sits behind a Cloudflare bot challenge with `ai-train=no` content signals.

Full probe log, with an HTTP status for every URL, is in [review.yml](review.yml).

## Switching Cost

The point of this profile. Summarised from the `switchingCost` block in [review.yml](review.yml).

| Dimension | Finding |
| --- | --- |
| Interface shape | `none-published` — the standards in play (GDS EDIFACT, ATPCO fare filing, IATA Resolution 824, BSP/ARC settlement, SFPD) all belong to intermediaries, not to Porter |
| Second source | `no-alternative` — the channel is swappable (Sabre, Travelport, aggregators), the supplier is not |
| Exit path | `export-on-request` — a written PIPEDA access request to Porter's Privacy Officer, 30-day response; no export operation exists because no API exists |
| Identifier portability | Mostly shared industry keys (PD, 451, POE, PNR locators, BSP/ARC documents, IATA/TIDS agency numbers, ATPCO fare bases, SFPD) plus proprietary VIPorter numbers |
| Contractual lock-in | Published and specific — see below |
| Distribution model | `gds-intermediated` |
| NDC posture | None. No certification claimed, no endpoint published, NDC not referenced in any Porter agency document |
| Access gate | `accredited-or-licensed` — ARC accreditation or an IATA Passenger Sales Agency Agreement |

What the published terms actually say, from the Agency Terms and Conditions effective 2026-07-15:

- Porter may **suspend or terminate an appointment immediately, at sole discretion**, on written notice. No minimum term and no notice period is published.
- All **"Porter Data" is owned by Porter** and is its Confidential Information — including every PNR and all booking and payment data.
- **Data rights end at termination**: prohibited uses include "accessing or using or distributing Porter Data for any purpose after Agent's authority has been suspended or terminated."
- **No scraping**: "screen scraping, spiders, web 'bots' or other automated means" are prohibited.
- **No redistribution**: an appointment "does not include any authority for Agent to act as an intermediary for distribution of Porter's products and services via third parties" unless Porter is a party to the arrangement. EU/UK ccTLD sites are carved out.
- **Service-fee MFN**: an agency's fee on a Porter booking "must be equal to the lowest fee imposed by Agent for other air carriers."
- **Metasearch ban**: no bidding on Porter content through Kayak and Skyscanner, and no buying search terms containing "Porter."
- **Association exclusivity**: "The Agency agrees not to join and be a member of more than one travel association or group at the same time."
- **Sabre-specific**: passive segments may be booked through any GDS except Sabre.
- Debit memos carry a **$25.00 to $75.00 administrative fee** each.

## Properties

- [Website](https://www.flyporter.com/)
- [Travel Agent Portal](https://www.flyporter.com/en-ca/services/travel-agents)
- [Agency Registration](https://www.flyporter.com/en-ca/services/travel-agents/agency-registration)
- [Travel Agent Sign In](https://www.flyporter.com/en-ca/services/travel-agents/sign-in)
- [Agency Terms and Conditions](https://www.flyporter.com/Content/Documents/TravelAgents/en/terms-and-conditions.pdf)
- [Booking and Ticketing Policy](https://www.flyporter.com/Content/Documents/TravelAgents/en/booking-and-ticketing-policy.pdf)
- [Standard Commission Policy](https://www.flyporter.com/Content/Documents/TravelAgents/en/porter-airlines-commission-policy.pdf)
- [Privacy Policy](https://www.flyporter.com/en-ca/privacy)
- [Agency Support](https://porteragency.zendesk.com/hc/en-ca/requests/new)
- [Media Centre](https://www.flyporter.com/en-ca/about-porter/media-centre)
- [IATA Member Profile](https://www.iata.org/en/about/members/airline-list/porter-airlines/670/)

## Maintainers

- Kin Lane — kin@apievangelist.com
