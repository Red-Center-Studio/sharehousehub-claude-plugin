---
name: find-safe-room
description: Guides seekers through finding a sharehouse or flatshare room safely across AU, NZ, UK, CA, US, and IE using search_rooms, estimate_room_cost, scam_check, and tenancy_basics. Use when searching for a room, flatshare, or roommate setup, comparing weekly/monthly rent, or checking an external listing.
---

# Find a Safe Sharehouse or Flatshare Room

Walk a room seeker through finding, budgeting, and safety-checking a shared-housing room across Australia, New Zealand, United Kingdom, Canada, United States, or Ireland.

## Workflow

1. **Search available rooms (`search_rooms`):**
   - Collect preferred suburb/neighbourhood (`locality`), region/state (`region` or `state`), `country_code` (`AU`, `NZ`, `UK`, `CA`, `US`, `IE`), maximum rent + cadence (`weekly`, `biweekly`, `monthly`), and target move-in date.
   - Call `search_rooms` and `get_listing` on top picks (listings return locality only, never street addresses, phones, or emails).
   - If nothing matches yet, offer `save_search` once signed in and proceed with cost and safety tools.

2. **Calculate true weekly/monthly & upfront cost (`estimate_room_cost`):**
   - Call `estimate_room_cost` with `country_code`, `currency`, `rentAmount`, `rent_cadence`, `billsIncluded`, `estimatedBillsAmount`, `housemates`, `depositWeeks`, and `advanceWeeks`.
   - Present weekly, fortnightly, monthly, and total upfront cash in the local currency.

3. **Check jurisdiction bond/deposit & tenancy rules (`tenancy_basics`):**
   - Call `tenancy_basics` with `country_code`, `state` (AU) or `region` (e.g. `ENG`, `SCT`, `ON`, `BC`, `NY`, `CA`, `NZ`, `IE`), and `arrangement` (`co_tenant`, `sub_tenant`, `rooming`, `boarder_lodger`).
   - Highlight local deposit terms (bond, tenancy deposit, security deposit), statutory protection schemes (RBO/RTBA/RTA, NZ Bond Centre, UK DPS/MyDeposits/TDS, RTB Ireland), notice periods, and include the non-legal-advice disclaimer.

4. **Check suspicious external ads (`scam_check`):**
   - For pasted ads or URLs from Facebook Marketplace, SpareRoom, Flatmates, Gumtree, Craigslist, Kijiji, Daft, or TradeMe, call `scam_check` with `text`, optional `sourceUrl`, and `country_code`.
   - Report the `riskScore`, `riskLevel`, and matched signals without declaring a final verdict, and remind seekers to inspect in person before paying a deposit.
