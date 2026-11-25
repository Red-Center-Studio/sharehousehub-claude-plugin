---
name: fill-my-room
description: End-to-end host workflow for international sharehouses and flatshares: create/update listings atomically with no-login /apply links, filter and shortlist applicants, manage multi-currency rent ledgers, generate jurisdiction-aware house agreements or gated viewing invites, and prepare handover checklists.
---

# Fill & Manage My Sharehouse / Flatshare

Guide hosts across AU, NZ, UK, CA, US, and IE through listing a room, triaging applicants, scheduling rent, and generating household notices in minimal turns.

## Workflow

1. **Create or update the listing atomically (`create_listing_draft` / `update_listing`):**
   - Gather `locality` (suburb/neighbourhood), `region` / `state`, `country_code`, `currency`, `rent_cadence` (`weekly`, `biweekly`, `monthly`), `rentAmount`, `depositAmount` / `depositTerms`, `availableFrom`, `quietHours`, `cleanlinessLevel`, `rules`, and `description`.
   - Call `update_listing` to adjust price, cadence, rules, availability, or status in one call and return the refreshed shareable no-login `/apply` link preview (`applyUrl`).

2. **Triage and shortlist `/apply` applicants (`filter_applicants` + `pro_screen_applicant`):**
   - Call `filter_applicants` with thresholds (`minFitScore`, `minSafetyScore`, `moveInFrom`, `moveInTo`, `requireBudgetMatch`, `nonSmokerOnly`, `petFreeOnly`, `verifiedContactOnly`) to get a ranked shortlist based on borderless compatibility and safety signals.
   - Optionally call `pro_screen_applicant` for tailored viewing-invite or polite-decline message drafts.

3. **Generate viewing invites, house rules, and welcome packs (`generate_sharehouse_document`):**
   - Call `generate_sharehouse_document` with `documentType: "viewing_invitation"`. Only set `addressRevealApproved: true` once the host explicitly approves sharing the exact street address.
   - Generate `house_rules_agreement` for jurisdiction-accurate deposit/notice terms and `welcome_pack_and_receipt` on move-in.

4. **Track room rent splits & reminders (`record_rent_ledger` + `get_rent_ledger`):**
   - Set up weekly, biweekly, or monthly room schedules with `record_rent_ledger` (`action: "setup_schedule"`) and log partial or full payments (`action: "log_payment"`).
   - Call `get_rent_ledger` to view balances and generate ready-to-send overdue or upcoming rent reminders in the house's local currency.
   - Use `pro_handover_checklist` (SharehousePro) for check-in/check-out inspections and deposit deduction reconciliation.

## Live connector note

On the live connector the applicant, rent ledger and Pro tools named above (`filter_applicants`, `pro_screen_applicant`, `record_rent_ledger`, `get_rent_ledger`, `pro_handover_checklist`) are not listed yet. What works now: `create_listing_draft` and `update_listing` for the listing, `scam_check` on the ad text, `inspection_checklist` (role host) for meeting people safely, `draft_message` for replies the host sends themselves, and `generate_sharehouse_document` for a house agreement outline.
