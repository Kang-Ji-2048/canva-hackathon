# Magic Write pass (mandatory: slogan, value proposition, pitch script)

The brief says the slogan, value proposition and pitch script must come from Canva AI / Magic Write. Everything on the site is a draft until this pass is done.

## How to run it (about 15 minutes)
1. In Canva, create a **Doc** called "Receipts copy (Magic Write)". Keep it: it's your evidence if judges ask.
2. Type `/` and choose **Magic Write** (or use the Canva AI panel). Paste **Prompt 0** first, then each prompt below in turn.
3. **Screenshot each prompt and its result** before editing anything.
4. Pick the winners, paste them into the "Chosen" column below (or paste them into the project chat), and the team will swap them into `index.html`, `demo.html` and `og.png`.

Rule of thumb: keep Magic Write's wording where it's good. Only fix facts (pledges, payout rules, Sunday 6pm and proposed pricing) and length.

---

### Prompt 0: brand context (paste first)
> Receipts is a student startup prototype for friend screen-time competitions. Groups pledge £5, £10 or £20 each per week. Each person's share of the pot is proportional to how far their screen time finishes below the group's highest total. Highest usage gets £0; if everyone ties, pledges are returned. Results and an itemised receipt arrive Sunday at 6pm. Receipts show time by app, place, pledge, return and net. The demo uses sample data and moves no real money. Daily-limit charity stakes are an earlier secondary prototype. Free and £2.99/month Pro pricing are proposals; final pricing and feature allocation are unconfirmed. Audience: UK students and Gen Z. Tone: playful, kind, never shaming. British English.

### Prompt 1: slogan
> Write 10 slogans for Receipts, max 5 words each. Use the receipt/itemised idea. One of them can be "Your scrolling, itemised." if nothing beats it.

### Prompt 2: value proposition (hero subhead)
> Write 5 value propositions for the Receipts landing page hero, max 30 words each. Mention pledging with friends, less scrolling for a bigger share of the pot, and the Sunday 6pm receipt. Do not promise a profit.

### Prompt 3: problem hook
> Write 5 two-line hooks about how easy it is to ignore app limits and how a shared pledge gives friends a reason to scroll less together. Max 20 words total each. Avoid claims of proven effectiveness.

### Prompt 4: section headlines
> Write 3 options each, max 6 words, for these landing page headings: (a) How the friend competition works, (b) the shareable Sunday receipt, (c) how the pot is shared, (d) proposed pricing, still unconfirmed, (e) final call to join the waitlist.

### Prompt 5: pitch script (60 seconds)
> Write a 60-second pitch script (about 150 spoken words) for Receipts for hackathon judges. Structure: hook → ignored app limits → friend competition with a live demo moment ("watch the Sunday reveal") → receipt with pledge, return and net → proposed subscription model, with final pricing unconfirmed → slogan. Say the demo uses sample data and moves no money. Do not present sample results as evidence of behaviour change.

### Prompt 6 (optional): FAQ answers
> Write friendly FAQ answers, max 45 words each: "What if I can’t afford it?", "Where does the pot go?", "Can Receipts see what I watch?", "Can I change the group rules?" Use Prompt 0’s facts. The demo tracks nothing. Changes to pledge and counted apps start next week.

---

## Swap table

| Slot | Current draft | Chosen (from Magic Write) |
|---|---|---|
| Slogan / hero headline | Your scrolling, itemised. | |
| Value prop / hero subhead | Pledge £5, £10 or £20 with friends. Scroll less for a bigger share of the pot. Your results and receipt arrive Sunday at 6pm. | |
| Problem hook | Ignoring a limit is easy. / Give your friends a reason to notice. | |
| How it works heading | Three steps. One receipt. | |
| Receipt heading | Made to be screenshotted. | |
| Competition heading | Less scrolling. A bigger share. | |
| Pricing heading | A proposal. Still taking shape. | |
| Final CTA heading | Close the app. Open the waitlist. | |
| Pitch script | Pending the competition-focused Magic Write pass | |

The full list of every string on the page is in `HANDOVER.md` (each is tagged `<!-- COPY: id -->` in the HTML).
