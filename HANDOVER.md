# Receipts landing page: handover

Files: `index.html` (landing page: one self-contained file, inline CSS and JS, Google Fonts with system-font fallbacks, no framework), `demo.html` (app demo), `og.png` + `og-card.html` (link-preview image and its source), `MAGIC-WRITE.md` (Magic Write prompts). I tested it at 390px and 1100px wide. On a phone the hero CTA sits at about 470px from the top, so it's above the fold.

## Canva Code compatibility (checked 1 Oct 2026)

What Canva's help centre says:
- Canva Code is **prompt-driven**. Canva says code "can't be exported as a file or directly edited within Canva". You can view and copy the generated code, but there is **no documented way to paste your own HTML**. ([Canva Code](https://www.canva.com/help/canva-code/), [Edit Canva Code designs](https://www.canva.com/help/canva-code-generated-interactive-elements/))
- A Canva Code design **can be published as its own website** (Publish → choose URL). An oversized widget can block publishing. ([Publish Canva Code](https://www.canva.com/help/publish-canva-code/))
- The docs don't say anything about external fonts, network requests or form submissions.

What this means:
1. **Plan A (test this first, about 5 minutes):** open Canva Code and prompt: *"Build this exact page. Reproduce the following HTML verbatim; do not redesign or rewrite it:"* followed by the whole file. AI tools usually comply, but this is **unverified**. Check the preview, then Publish.
2. **Plan B:** if Canva rewrites or truncates the code, build the page as a normal Canva Website, using the brand colours and fonts below and the copy list. Then use Canva Code for the animated hero receipt only (prompt it with the `.receipt` block plus its CSS).
3. The file is built to survive a sandbox: if Google Fonts are blocked it falls back to system fonts, it doesn't use localStorage, and the form uses `preventDefault`. Its only network call is the optional Google Form submission (see Waitlist). Canva's sandbox may block that call, so test a sign-up on the live page.

## Waitlist form

**Right now nothing is stored.** The form checks the email address, shows "You're on the list ✓ #1,248 in the queue" and adds one to a demo counter.

The code is ready to send sign-ups to a **Google Form**, which lands them in a Google Sheet. It needs two values that only exist once you create the form (first check that the hackathon allows non-Canva tools):
1. Go to forms.google.com → Blank form → title "Receipts waitlist" → one **Short answer** question called "Email" (⋮ → Response validation → Text → Email).
2. Settings → Responses: turn **off** "Restrict to users in [your org]" and "Collect email addresses". A UCL account restricts forms to UCL users by default, which would silently drop outside sign-ups; a personal Google account avoids this.
3. Send → link icon → copy the link (`.../forms/d/e/<long id>/viewform`). **Paste it to Claude.** Claude reads the form ID and the email field's `entry.` number and fills in `WAITLIST` near the bottom of `index.html`.
4. Responses tab → Link to Sheets, so the team sees sign-ups live.

Limits: Google doesn't let the page read the reply, so the page can only report network failures. A form that's misconfigured (e.g. still restricted) will look successful while dropping the email, so after publishing, sign up once yourself and check the Sheet. The counter stays a demo number.

## Assumptions I made (change any of these)
- **Problem stat:** I didn't use an attributed statistic. The page shows arithmetic: 2h/day × 365 ≈ 30 days a year, labelled "Just maths, not a survey".
- **Sample receipt convention:** Week 39 is the baseline example, **21–27 Sep 2026**: 15h 50m against a 2h/day limit gives 1h 50m over and an illustrative £11 donation. "Dodged £6" illustrates money you would have avoided paying by closing the app on time. Week 40 is the following sample week, **28 Sep–4 Oct 2026**: the landing-page phone mock illustrates 9h 50m and £3 donated, a hypothetical 6h reduction. Its friend-pot receipts are separate full-week examples. All receipts, exported receipt images and sample stats are illustrative, not real tracking, real donations or evidence of improvement.
- **"Capped daily, so a bad night never becomes a bad month"** in Stakes mode: I added this to keep the tone kind. It's a product decision, so remove it if the team disagrees.
- **"STUDENT PRICE"** tag on Pro, and **"Launching on campus soon"** above the final CTA.
- **1,247 queued** is a demo counter. There are no testimonials.
- **Contact email** `hello@receipts.app` is a placeholder (the team doesn't own that domain). Swap in a real inbox the team checks. Instagram/TikTok footer links are still `#`.
- **Privacy note** says sign-ups are kept in a private list only the team can see, used only for the launch email, and deleted on request. Keep it true: if you use something other than a private Google Form/Sheet, update it.
- **FAQ answers** restate the daily cap and "we only see time per app". The second one is a product promise; the team should agree with it.

## Still to do in Canva
- Run the Magic Write pass: prompts and a swap table are in `MAGIC-WRITE.md` (a brief requirement; keep screenshots as evidence).
- Apply the team brand kit if its hex values differ: paper `#F7F5EF`, ink `#1A1A1A`, red `#E5322D`, fonts Space Grotesk + JetBrains Mono. They're at the top of the `<style>` block.
- Publish, set the site URL, and test the live link on a phone.
- Decide on a real form (see above).
- **Share preview:** after publishing, replace `https://REPLACE-WITH-SITE-URL` in the `<head>` of `index.html` with the live address and host `og.png` alongside it. Canva-published sites can't host a loose image file, so if the page lives on Canva, either use the site's own social-preview setting (if your plan has one) with `og.png`, or host `og.png` anywhere public (e.g. the GitHub Pages/Netlify fallback) and point `og:image` at that URL. Then test by pasting the link into WhatsApp. `og.png` is rendered from `og-card.html`; re-render after copy changes (ask Claude, or open it at 1200×630 and screenshot).

## Copy strings for Magic Write
Each one is tagged `<!-- COPY: id -->` in `index.html`.

| id | Current text |
|---|---|
| hero-eyebrow | ● Pre-launch · Built for students |
| hero-headline (slogan) | Your scrolling, itemised. |
| hero-subhead (value prop) | Go over your daily TikTok and Instagram limit and every 10 minutes costs £1, all of it to a charity you choose. Every Sunday, you get the receipt. |
| cta | Join the waitlist |
| success | You're on the list ✓ |
| hero-fineprint | Free plan at launch · One email when we go live. That's it. |
| problem-number | 30 days |
| problem-lede | Two hours of scrolling a day is a whole month of your year. Gone. |
| problem-footnote | Just maths, not a survey: 2h × 365 = 730h ≈ 30 days. |
| problem-hook | Blockers fail because ignoring them is free. We make it cost £1. |
| how-heading | Three steps. One receipt. |
| step1-title / body | Set your limit / Pick a daily cap for TikTok and Instagram. One hour? Two? Your call. |
| step2-title / body | Go over, pay £1 / Every 10 minutes past your limit costs £1, and 100% of it goes to charity. |
| step3-title / body | Get your Sunday receipt / Where your hours and your money went. Share it, or keep it to yourself. |
| receipt-heading | Made to be screenshotted. |
| receipt-tick1–4 | Every hour, itemised by app · What that time could have been · £ donated vs. £ dodged · One tap to your story. Flex the good weeks, roast the bad ones. |
| charity-heading | Every £1 goes to charity. We never take a cut. |
| charity-sub | We make money from Pro subscriptions, never from your slip-ups. Stakes are opt-in, and you can switch them off any time. |
| stakes-title / body | Your limit, your money on it / £1 per 10 minutes over. Capped daily, so a bad night never becomes a bad month. |
| pots-title / body | Scroll less, together / Set limits as a group. Every slip goes into a shared pot for your group's charity. |
| pricing-heading | Cheaper than one meal deal. |
| soon-title / body | The revision feed / A scrollable feed made from your own lecture slides. Scroll it to earn your minutes back. |
| final-heading | Close the app. Open the waitlist. |
| counter | 1,247 students already queued |
| footer-line | *** Thank you for scrolling responsibly *** |
| demo-link | Try the demo → |
| pricing-money | Pro pays for Receipts. Your donations never do. |
| faq-heading | Fair questions. |
| faq1 | What if I can't afford it? / Stakes are opt-in and capped daily, so one bad night never becomes a bad month. The Free plan has no stakes at all, just the receipt. |
| faq2 | Which charities does the money go to? / You pick a cause: mental health, education or climate. We'll announce our charity partners at launch, and 100% of every £1 is passed on. |
| faq3 | Can Receipts see what I watch? / No. Receipts only sees how long each app was open. Never what you watched, posted or messaged. |
| faq4 | Can't I just delete the app? / Sure. But you set the stakes because future you asked present you to. And with a friend pot, your mates will notice. |

## App demo (`demo.html`)
- This is a clickable prototype, and all of its data is fake and lives only in the page. **No money moves**: pots and payouts are simulated.
- **Two models in one demo.** The first prototype's daily limits (Today · Receipt · Stats, plus Limits and the charity picker) sit alongside the friend competition (Compete · Group, plus the Sunday reveal). Tabs: Today · Receipt · Compete · Stats · Group. Stats combines your competition record (this week, position, winnings, time by app, weekly chart, past competitions) with the daily-limits charts below it. Onboarding creates or joins a group and lands on Compete. Limits opens from the sliders icon on Today.
- **Demo start state.** The first week opens already finished: Compete shows a red "results are in" card, so the Sunday reveal is one tap away. After "Start next week" the countdown runs live.
- **Secret triggers.** Today logo: tap 3× or long-press to go 10 min over (£1 to charity, up to the £5/day cap). Compete logo: tap 3× to skip to Sunday 6pm, or long-press to add 30 min of scrolling (your position can drop).
- **Competition.** Pot = pledge × members (£5/£10/£20). The countdown runs to the real next Sunday 6pm. During the week you see only your own time and place; everyone else's is hidden. Group settings (pledge, apps counted) and invites take effect next week. New groups count all five apps by default.
- **Payout rule.** Proportional: your share is proportional to how far you finished below the group's highest total, so last place gets £0. Ties share a place. Default numbers: Charles 3h 12m, you 4h 01m, Priya 5h 20m, Dan 7h 45m, Sam 9h 30m, which splits £50 as £17.80 / £15.49 / £11.77 / £4.94 / £0.
- **Reveal.** Your week (with time saved vs last week and since your first week), then the leaderboard from last to first, then the receipt (same component, itemising time, time saved, place, pledge and winnings) with share/download, then a single "go again" button (same group and pledge).
- **Stats** (daily limits): illustrative weekly hours for weeks 32–39 of 2026 and Week 39 (**21–27 Sep 2026**) by day, with the time within the limit in ink and the time over it in red. There's also an illustrative breakdown of donations by charity. Tap a bar for details. The Week 39 by-day figures add up to the sample Sunday receipt (15h 50m, 1h 50m over, £11); none of these figures represents real tracking or donations.
- **Logo.** Mark A, "Ranked receipt" (a receipt whose printed lines are a leaderboard, 1st in the accent), chosen from the concepts in `logos.html`. It is used for the in-app logos, the notification banner, the favicon and the home-screen icon, which redraw in the current theme. `index.html` still uses the old mark.
- **Themes.** Six colour themes (Receipt, Night shift, Cobalt, Highlighter, Mint, Bubblegum): pick one with the dots on the start screen, or from Settings (gear icon on Compete and Today). The choice is saved in the browser where storage is allowed. All colours are CSS tokens at the top of `demo.html`; `themes.html` previews every theme with contrast checks. Receipt paper stays white in every theme so shared images look like a receipt.
- **Charity picker** (daily limits): the charities (Mind, YoungMinds, Samaritans, BookTrust, Teach First, Woodland Trust, ClientEarth) are **examples, not partners**, and the page says so.
- The landing page (`index.html`) still describes only the daily-limits and charity model. Update its copy if the competition becomes the pitch.
- The `Try the demo →` link in `index.html` points to the relative path `demo.html`. Once both are hosted, change it to the demo's full URL. A relative link won't resolve from a Canva-published page.
- To add it to the home screen, it must be served over https (Canva Code publish, Netlify Drop or GitHub Pages). On iOS, use Safari → Share → Add to Home Screen. The icon is drawn as a PNG at load time; that should work, but I haven't tested it on a real iPhone. Android needs a web manifest for true full-screen, and I didn't add one.
