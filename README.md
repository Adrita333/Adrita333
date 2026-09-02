Debadrita Choudhury
Regional head of data science and analytics — ~20 years across BFSI, CPG,
retail and insurance, leading teams of 80+ across multiple countries.
I still build. The four applications below are running right now, and you
can open any of them.
![The Maison Aurelle advisor brief — twelve ranked clients, three held back](assets/luxury-brief.png)
<sub>The clienteling co-pilot's daily brief. Regenerated every morning by a
scheduled job — the date in the header is today's.</sub>
---
Projects
	What it does	See it	Code
Luxury Clienteling Co-Pilot	A daily advisor brief for a luxury maison. Ranks which clients to contact, on which channel, with a drafted message — and holds back the ones it should not contact, with the reason shown	Open the brief	repo
Retail Invoice & Trade-Claim Agent	Reads retailer deduction claims, checks each against the governing supply contract, and returns a verdict with the clause it relied on	Open the app	repo
Customer Enquiry Triage Agent	Classifies and answers inbound customer enquiries in four languages, escalating anything it cannot substantiate	Open the app	repo
Demand Forecast Health Check	Runs five diagnostic gates over a demand history and ranks why the forecast is failing, by recoverable value — with validation tests designed to disprove its own findings	Open the app	repo
<sub>The three Streamlit apps are hosted free; if one shows a "wake app" button,
give it about 30 seconds.</sub>
---
What the numbers look like
Luxury clienteling co-pilot — 15 clients scored each morning; 12 surfaced with a ranked action, channel, timing and drafted message; 3 held back and shown with the reason.
Evidence is visible by default and the polished draft is collapsed, deliberately: an advisor who sees the message first will send it without reading why.
Retail invoice & trade-claim agent — 480 claims scored; 73% cleared automatically, 27% routed to a human.
US$29,725 of US$38,763 leakage identified. Zero incorrect rejections, against 10 in the manual baseline. All 263 clause citations came from the governing contract.
Customer enquiry triage agent — 900 enquiries a month across four languages, 63% of them not in English; 44% auto-answered.
~61% reduction in handling time, and 100% recall on health-related escalations — none of which are ever auto-answered.
Demand forecast health check — five failure modes ranked by recoverable value.
The two largest fixes cost nothing: a parameter in the replenishment rule, and one line in the scoring script. Four validation tests, three of which can fail.
---
How they are built
The same three-stage shape each time: run, store, ship. The pipeline
scores everything once and writes it down; the interface only reads. Nothing is
computed at display time, so the number on screen is the number that was measured.
Four things they have in common:
The answer key is quarantined. Only the evaluation stage may read it. Nothing
that produces a verdict can see it, which is what makes a scorecard a measurement
rather than a restatement.
Every output is citable. A verdict with no clause behind it is held, not sent.
An answer not in the approved library does not go out.
What was refused is shown. The clients not contacted, the claims held for
review, the series too young to forecast — all visible, with the reason. Most
systems only show what they decided to do.
The findings can fail. The forecasting agent ships tests designed to disprove
its own conclusions, and reports when one does.
All four run on synthetic data generated from a fixed seed, so every figure above
reproduces exactly. The faults in the data are ones I built in deliberately. On real
data the levels differ — what transfers is the method.
---
I'm always glad to talk about building and running analytics functions, and about
what AI actually changes inside an operating process — as opposed to what it is
said to change.
📧 dchoudhury.oct@gmail.com · 💼 LinkedIn
<sub>© 2026 Debadrita Choudhury. Published for evaluation, not licensed for reuse.</sub>
