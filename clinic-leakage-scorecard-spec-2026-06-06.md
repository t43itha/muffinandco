# Clinic Leakage Scorecard — build spec

Date: 2026-06-06
Purpose: turn Muffin & Co from a brochure funnel into an interactive diagnostic funnel.

## Funnel promise

**Find where your clinic is losing treatment enquiries before they become consultations.**

In 2 minutes, the clinic receives:

- leakage score,
- top 2 likely leaks,
- recommended first workflow,
- free review CTA,
- phone CTA: +44 20 4634 9555.

## Quiz questions

1. What type of clinic are you?
   - Aesthetic clinic
   - Skin clinic
   - Laser clinic
   - Dermatology clinic
   - Plastic surgery clinic
   - Other appointment-led clinic

2. What channel creates the most new enquiries?
   - Phone
   - WhatsApp
   - Instagram DMs
   - Website forms
   - Online booking
   - Not sure

3. Which channel gets missed or delayed most often?
   - Phone
   - WhatsApp
   - Instagram DMs
   - Website forms
   - Online booking
   - Not sure

4. How quickly do new enquiries usually receive a reply?
   - Under 5 minutes
   - 5–30 minutes
   - 30 minutes–2 hours
   - Same day
   - Next day or later
   - It depends who is on shift

5. Do you have a missed-call follow-up process?
   - Yes, automated
   - Yes, manual
   - Sometimes
   - No
   - Not sure

6. Do you qualify treatment enquiries before the consultation?
   - Yes, consistently
   - Sometimes
   - Mostly manually
   - No
   - Not sure

7. Do you send automated no-show or reschedule nudges?
   - Yes
   - Partly
   - No
   - Not sure

8. Do you send post-treatment aftercare and review requests?
   - Yes, automated
   - Yes, manual
   - Sometimes
   - No
   - Not sure

9. What is one booked consultation or treatment enquiry worth to you?
   - Under £100
   - £100–£250
   - £250–£500
   - £500–£1,000
   - £1,000+
   - Not sure

10. Where should we send the scorecard?
   - Name
   - Clinic
   - Email
   - Website
   - Optional phone

## Scoring model

Start at 0. Add leakage risk points:

- reply time over 30 minutes: +2
- reply time same day/later: +3
- “depends who is on shift”: +3
- no missed-call process: +3
- manual missed-call process: +1
- no qualification process: +2
- no no-show/reschedule nudges: +2
- no aftercare/review flow: +2
- “not sure” on any operational question: +1
- consultation value £500+: +1 because leakage has higher revenue risk

## Output bands

### 0–4: Low visible leakage

Message:

Your clinic has some good follow-up foundations. The opportunity is likely in polish and consistency rather than urgent recovery.

Recommended first workflow:

- post-treatment review capture, or
- consultation-to-treatment follow-up.

CTA:

Book a free review to find the highest-value polish point.

### 5–9: Moderate leakage

Message:

Your clinic likely has enquiry handoff gaps. These are the moments where interested clients wait, drift, or book elsewhere.

Recommended first workflow:

- WhatsApp/DM triage,
- missed-call follow-up,
- form-to-consultation routing.

CTA:

Book a free Clinic Leakage Review.

### 10+: High leakage

Message:

Your clinic may be losing treatment enquiries before they become consultations. The fastest win is a recovery workflow around the channel that gets missed most often.

Recommended first workflow:

- missed enquiry callback,
- WhatsApp response sequence,
- no-show recovery.

CTA:

Call +44 20 4634 9555 or book the free review.

## Email follow-up copy

Subject: Your Clinic Leakage Scorecard

Hi {{name}},

Here is the quick read from your scorecard:

Score: {{score}} / high risk threshold 10
Top likely leak: {{top_leak}}
First workflow to inspect: {{recommended_workflow}}

The practical next step is a 15-minute Clinic Leakage Review. We will look at your enquiry path across phone, WhatsApp, Instagram, website forms and booking links, then identify the first leak worth fixing.

You can reply here or call +44 20 4634 9555.

Warmly,
Tabby
Muffin & Co
https://muffinandco.xyz
hello@muffinandco.xyz

## Implementation note

Phase 1 can be static HTML/JS with mailto fallback. No backend needed yet.

Phase 2 should send submissions to a lightweight form backend or Google Sheet once traffic exists.
