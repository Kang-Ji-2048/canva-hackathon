# Magic Write pass (mandatory: slogan, value proposition, pitch script)

The brief says the slogan, value proposition and pitch script must come from Canva AI / Magic Write. Everything on the site is a draft until this pass is done.

## How to run it (about 15 minutes)
1. In Canva, create a **Doc** called "Receipts copy (Magic Write)". Keep it: it's your evidence if judges ask.
2. Type `/` and choose **Magic Write** (or use the Canva AI panel). Paste **Prompt 0** first, then each prompt below in turn.
3. **Screenshot each prompt and its result** before editing anything.
4. Pick the winners, paste them into the "Chosen" column below (or just paste them to Claude in chat), and Claude will swap them into `index.html`, `demo.html` and `og.png`.

Rule of thumb: keep Magic Write's wording where it's good. Only fix facts (prices, £1 per 10 min, 100%) and length.

---

### Prompt 0: brand context (paste first)
> We're Receipts, a student startup. Receipts puts a price on doomscrolling: you set a daily limit for TikTok and Instagram, every 10 minutes over costs £1, and 100% goes to a charity you choose (mental health, education or climate). We never take a cut. Every Sunday you get an itemised "receipt" of your week: hours per app, what that time equals (e.g. "= 2 essays"), £ donated vs £ dodged, designed to share to your story. Free plan: the Weekly Receipt. Pro, £2.99/month: Stakes mode, friend pots (group limits, shared pot for a group charity), custom limits. Audience: UK students and Gen Z. Tone: playful, a bit self-roasting, never preachy or shaming. Funny about the habit, kind to the person. British English.

### Prompt 1: slogan
> Write 10 slogans for Receipts, max 5 words each. Use the receipt/itemised idea. One of them can be "Your scrolling, itemised." if nothing beats it.

### Prompt 2: value proposition (hero subhead)
> Write 5 one-sentence value propositions for the Receipts landing page hero, max 30 words each. Must mention: daily limit, £1 per 10 minutes over, 100% to a charity you choose, the Sunday receipt.

### Prompt 3: problem hook
> Write 5 two-line hooks explaining why app blockers don't work (ignoring them is free) and how Receipts fixes it (ignoring costs £1 to charity). Max 15 words total each.

### Prompt 4: section headlines
> Write 3 options each, max 6 words, for these landing page headings: (a) How it works, (b) the shareable weekly receipt, (c) 100% goes to charity, we never take a cut, (d) pricing (£2.99/month, cheaper than a meal deal), (e) final call to join the waitlist.

### Prompt 5: pitch script (60 seconds)
> Write a 60-second pitch script (about 150 spoken words) for Receipts for hackathon judges. Structure: hook (Gen Z scrolling problem) → why blockers fail → Receipts solution with a live demo moment ("watch what happens when I go over my limit") → the Sunday receipt as the growth engine → business model (Free + Pro £2.99/month, we never take a cut of donations) → closing line with the slogan.

### Prompt 6 (optional): FAQ answers
> Write short, friendly answers (max 35 words) to: "What if I can't afford it?", "Which charities?", "Can Receipts see what I watch?", "Can't I just delete the app?" Stakes are opt-in and capped daily; charity partners announced at launch; we only see time per app.

---

## Swap table

| Slot | Current draft | Chosen (from Magic Write) |
|---|---|---|
| Slogan / hero headline | Your scrolling, itemised. | |
| Value prop / hero subhead | Go over your daily TikTok and Instagram limit and every 10 minutes costs £1, all of it to a charity you choose. Every Sunday, you get the receipt. | |
| Problem hook | Blockers fail because ignoring them is free. / We make it cost £1. | |
| How it works heading | Three steps. One receipt. | |
| Receipt heading | Made to be screenshotted. | |
| Charity heading | Every £1 goes to charity. We never take a cut. | |
| Pricing heading | Cheaper than one meal deal. | |
| Final CTA heading | Close the app. Open the waitlist. | |
| Pitch script | (the 60-second script in Claude's earlier demo-script reply) | |

The full list of every string on the page is in `HANDOVER.md` (each is tagged `<!-- COPY: id -->` in the HTML).
