# ScrollSaver landing page: handover

Files: `index.html` (landing page: one self-contained file, inline CSS and JS, Google Fonts with system-font fallbacks, no framework), `demo.html` (app demo), `og.png` + `og-card.html` (link-preview image and its source), `MAGIC-WRITE.md` (Magic Write prompts). I tested it at 390px and 1100px wide. On a phone the hero CTA sits at about 470px from the top, so it's above the fold.

## Canva Code compatibility (checked 1 Oct 2026)

What Canva's help centre says:
- Canva Code is **prompt-driven**. Canva says code "can't be exported as a file or directly edited within Canva". You can view and copy the generated code, but there is **no documented way to paste your own HTML**. ([Canva Code](https://www.canva.com/help/canva-code/), [Edit Canva Code designs](https://www.canva.com/help/canva-code-generated-interactive-elements/))
- A Canva Code design **can be published as its own website** (Publish → choose URL). An oversized widget can block publishing. ([Publish Canva Code](https://www.canva.com/help/publish-canva-code/))
- The docs don't say anything about external fonts, network requests or form submissions.

What this means:
1. **Plan A (test this first, about 5 minutes):** open Canva Code and prompt: *"Build this exact page. Reproduce the following HTML verbatim; do not redesign or rewrite it:"* followed by the whole file. AI tools usually comply, but this is **unverified**. Check the preview, then Publish.
2. **Plan B:** if Canva rewrites or truncates the code, build the page as a normal Canva Website, using the brand colours and fonts below and the copy list. Then use Canva Code for the animated hero receipt only (prompt it with the `.receipt` block plus its CSS).
3. The file is built to survive a sandbox: if Google Fonts are blocked it falls back to system fonts, it doesn't use localStorage, and the demo opens through ordinary links. Deploy the landing page and demo together, then check the links on the live page.

## Demo entry

The navbar, hero and final call to action all say **Try the demo** and link to `demo.html`. Deploy both HTML files in the same directory. If the landing page is rebuilt in Canva and the demo is hosted elsewhere, use the demo's full published URL instead. There is no email form, sign-up counter or subscription pricing section.

## Assumptions I made (change any of these)
- **Problem stat:** I didn't use an attributed statistic. The page shows arithmetic: 2h/day × 365 ≈ 30 days a year, labelled "Just maths, not a survey".
- **Sample receipt convention:** the landing page, Receipt tab and share card use one simulated competition result for Week 40, **28 Sep–4 Oct 2026**: Flat 4B, five friends, £10 pledged each, £50 pot; you scroll 4h 01m, finish 2nd and receive £15.49 (+£5.49 net). App totals are Instagram 1h 28m, TikTok 1h 12m, YouTube 46m, Snapchat 20m and Reddit 15m. These are illustrative fixtures, not evidence of improvement or real transactions.
- **Optional daily limits:** TikTok and Instagram limits are pacing reminders only. Going over still counts towards the weekly competition and never triggers a separate payment.
- **Contact email** `hello@receipts.app` is a placeholder (the team doesn't own that domain). Swap in a real inbox the team checks. Instagram/TikTok footer links are still `#`.
- **Privacy note:** the landing page collects no email addresses; the demo uses sample data and may save the theme preference locally.
- **App privacy:** the demo tracks nothing. Time-per-app-only access is a planned product requirement, not an implemented integration.

## Still to do in Canva
- Run the Magic Write pass: prompts and a swap table are in `MAGIC-WRITE.md` (a brief requirement; keep screenshots as evidence).
- Apply the team brand kit if its hex values differ: paper `#F7F5EF`, ink `#1A1A1A`, red `#E5322D`, fonts Space Grotesk + JetBrains Mono. They're at the top of the `<style>` block.
- Publish, set the site URL, and test the live link on a phone.
- **Share preview:** after publishing, replace `https://REPLACE-WITH-SITE-URL` in the `<head>` of `index.html` with the live address and host `og.png` alongside it. Canva-published sites can't host a loose image file, so if the page lives on Canva, either use the site's own social-preview setting (if your plan has one) with `og.png`, or host `og.png` anywhere public (e.g. the GitHub Pages/Netlify fallback) and point `og:image` at that URL. Then test by pasting the link into WhatsApp. `og.png` is rendered from `og-card.html`; re-render after copy changes (ask Claude, or open it at 1200×630 and screenshot).

## Copy strings for Magic Write
Each one is tagged `<!-- COPY: id -->` in `index.html`.

| id | Current text |
|---|---|
| hero-eyebrow | ● Pre-launch · Built for students |
| hero-headline (slogan) | Your scrolling, itemised. |
| hero-subhead (value prop) | Pledge £5, £10 or £20 with friends. Scroll less for a bigger share of the pot. Your results and receipt arrive Sunday at 6pm. |
| cta | Try the demo |
| hero-fineprint | Interactive prototype · Sample data · No real money moves. |
| problem-number | 30 days |
| problem-lede | Two hours of scrolling a day is a whole month of your year. Gone. |
| problem-footnote | Just maths, not a survey: 2h × 365 = 730h ≈ 30 days. |
| problem-hook | Ignoring a limit is easy. Give your friends a reason to notice. |
| how-heading | Three steps. One receipt. |
| step1-title / body | Make your group / Choose a weekly pledge: £5, £10 or £20 each. Everyone puts in the same. |
| step2-title / body | Scroll less, together / Your share grows with the gap between your screen time and the group's highest total. |
| step3-title / body | Get your Sunday receipt / Sunday at 6pm: reveal the standings, your return and your weekly receipt. |
| receipt-heading | Made to be screenshotted. |
| receipt-tick1–4 | Time in each counted app · Your place in the group · Pledged, returned and net · Share your receipt or download the image. |
| pot-heading | Less scrolling. A bigger share. |
| pot-sub | Everyone pledges the same amount. The pot is divided in proportion to how far each person finishes below the group's highest screen time. |
| stakes-title / body | Your pledge, your group / Highest screen time gets £0. If everyone ties, pledges are returned. Settings changes start next week. |
| pots-title / body | Fair from Monday to Sunday / Pledge and counted-app changes start next week, so everyone competes under the same settings. |
| soon-title / body | The revision feed / A lecture-slide revision feed concept. Not part of the current competition demo. |
| final-heading | Your next scroll, itemised. |
| footer-line | *** Thank you for scrolling responsibly *** |
| faq-heading | Frequently asked questions. |
| faq1 | What if I can't afford it? / Explore this demo free, with no real payment. The competition models pledges of £5, £10 or £20. A return can be £0. |
| faq2 | Where does the pot go? / The competition pot is shared among the group according to screen time. Highest usage gets £0; if everyone ties, all pledges are returned. |
| faq3 | Can ScrollSaver see what I watch? / This demo uses sample data and tracks nothing. The planned app would use time per app, never what you watched, posted or messaged. |
| faq4 | Can I change the group rules? / Yes. Changes to the pledge and counted apps take effect next week, so everyone finishes the current week under the same rules. |

## App demo (`demo.html`)
- This is a clickable prototype, and all of its data is fake and lives only in the page. **No money moves**: pots and payouts are simulated.
- **One competition model.** Tabs are Today · Receipt · Compete · Stats · Group. Today shows optional pacing limits and the current group pot; Receipt shows the latest competition result; Stats combines the competition record with optional-limit charts. Onboarding creates or joins a group and lands on Compete. Limits opens from the sliders icon on Today.
- **Demo start state.** The first week opens already finished: Compete shows a red "results are in" card, so the Sunday reveal is one tap away. After "Start next week" the countdown runs live.
- **Secret triggers.** Today logo: tap 3× or long-press to go 10 min over the optional TikTok limit. Compete logo: tap 3× to skip to Sunday 6pm, or long-press to add 30 min of scrolling (your position can drop).
- **Competition.** Pot = pledge × members (£5/£10/£20). The countdown runs to the real next Sunday 6pm. During the week you see only your own time and place; everyone else's is hidden. Group settings (pledge, apps counted) and invites take effect next week. New groups count all five apps by default.
- **Payout rule.** Proportional: your share is proportional to how far you finished below the group's highest total, so last place gets £0. Ties share a place. Default numbers: Charles 3h 12m, you 4h 01m, Priya 5h 20m, Dan 7h 45m, Sam 9h 30m, which splits £50 as £17.80 / £15.49 / £11.77 / £4.94 / £0.
- **Reveal.** Your week (with time saved vs last week and since your first week), then the leaderboard from last to first, then the receipt (same component, itemising time, time saved, place, pledge and amount returned) with share/download, then a single "go again" button (same group and pledge).
- **Stats** (daily limits): illustrative weekly hours for weeks 32–39 of 2026 and Week 39 (**21–27 Sep 2026**) by day, with the time within the limit in ink and the time over it in red. Tap a bar for details. None of these figures represents real tracking.
- **Brand.** The product name is **ScrollSaver**. The landing page, demo, notification banner and share card use the team's arcade-machine artwork in `icons/`, matching the favicon and home-screen icon (source: `icons/app-icon-source.png`; 32, 180, 192 and 512px exports). Note it shows a $ coin while the app uses £. Earlier receipt-mark concepts remain in `logos.html`.
- **Themes.** Six colour themes (Receipt, Night shift, Cobalt, Highlighter, Mint, Bubblegum): pick one with the dots on the start screen, or from Settings (gear icon on Compete and Today). The choice is saved in the browser where storage is allowed. All colours are CSS tokens at the top of `demo.html`; `themes.html` previews every theme with contrast checks. Receipt paper stays white in every theme so shared images look like a receipt.
- **Receipt preload.** The Receipt tab's 720×1080 share image is prepared after the theme is applied, cached while its content and theme are unchanged, and reused on repeat visits.
- The **Try the demo** links use `demo.html`; deploy both HTML files in the same directory.
- To add it to the home screen, it must be served over https (Canva Code publish, Netlify Drop or GitHub Pages). On iOS, use Safari → Share → Add to Home Screen. The icon is drawn as a PNG at load time; that should work, but I haven't tested it on a real iPhone. Android needs a web manifest for true full-screen, and I didn't add one.
