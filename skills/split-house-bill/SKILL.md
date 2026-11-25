---
name: split-house-bill
description: Guides sharehouse and flatshare hosts or roommates through extracting electricity, gas, water, or internet bill details and splitting costs pro-rata in local currency (AUD, NZD, GBP, CAD, USD, EUR) via pro_split_utility_bill.
---

# Split a House Utility Bill Pro-Rata

Help a sharehouse or flatshare coordinator split a utility bill fairly in any supported currency (`AUD`, `NZD`, `GBP`, `CAD`, `USD`, `EUR`) based on exact occupancy dates and days away.

## Workflow

1. **Extract bill details:**
   - From the user's message or uploaded bill image/PDF, extract `country_code` / `currency`, `utilityType`, `billTotal`, optional `supplyCharge`, `billingStart`, and `billingEnd` (`YYYY-MM-DD`).
   - Gather each housemate/roommate's name, optional `moveInDate` / `moveOutDate`, and `daysAway`.

2. **Run exact pro-rata calculation (`pro_split_utility_bill`):**
   - Call `pro_split_utility_bill`. Fixed supply charges split by occupied days; usage charges split by active days present (`occupiedDays - daysAway`), reconciled to exact cents.

3. **Present results or upgrade prompt:**
   - Share the itemized currency breakdown and `groupChatSummary` ready to copy into the house chat.
   - If `PLAN_UPGRADE_REQUIRED` is returned, explain what **Sharehouse Manager (\$6.99/mo)** and **SharehousePro (\$9.99/mo)** unlock and share `pricingUrl` (`https://sharehousehub.com.au/pricing`).

## Live connector note

On the live connector at mcp.sharehousehub.com.au the usage-based tool `pro_split_utility_bill` is not listed yet. Use `split_house_costs` instead: it splits weekly rent (equally or by room weight) and shared bills between housemates and needs no account. Say clearly that day-by-day usage splitting is not available yet.
