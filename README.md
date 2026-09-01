## Debadrita Choudhury

Data science and analytics leader, ~20 years across BFSI, CPG, retail and insurance.
I build the solution as well as the strategy — the repos below are working
applications, not prototypes, and two of them you can open and use right now.

---

### ▶︎ Live demos

| | What it does | Try it |
|---|---|---|
| **Retail Invoice & Trade-Claim Agent** | Reads retailer deduction claims, checks each against the governing supply contract, returns a verdict with the clause it relied on | **[Open the app](https://retail-invoice-agent.streamlit.app/)** · [code](https://github.com/Adrita333/retail-invoice-agent) |
| **Customer Enquiry Triage Agent** | Classifies and answers inbound customer enquiries in four languages, escalating anything it cannot substantiate | **[Open the app](https://customer-enquiry-agent.streamlit.app/)** · [code](https://github.com/Adrita333/Customer-enquiry-agent) |
| **Demand Forecast Health Check** | Runs five diagnostic gates over a demand history and ranks *why* the forecast is failing, by recoverable value | [code](https://github.com/Adrita333/demand-forecast-agent) |

*Hosted free on Streamlit Community Cloud. If an app shows a "wake app" button,
give it about 30 seconds — free apps sleep after 12 hours without traffic.*

---

### What the numbers look like

**Retail invoice agent** — 480 claims scored. 73% cleared automatically, 27% routed
to a human. US$29,725 of US$38,763 leakage identified. Zero incorrect rejections,
against 10 in the manual baseline. 263 clause citations, none from a
non-governing contract.

**Customer enquiry agent** — 900 enquiries a month across four languages, 63% of
them not in English. 44% auto-answered, ~61% reduction in handling time,
100% recall on health-related escalations — none of which are ever auto-answered.

**Demand forecast health check** — five failure modes ranked by recoverable value,
with four validation tests. Three of those tests can fail.

---

### How they are built

The same three-stage shape each time: **run**, **store**, **ship**. The pipeline
scores everything once and writes it down; the interface only reads. Nothing is
computed at display time, so the number on screen is the number that was measured.

Three things they have in common:

- **The answer key is quarantined.** Only the evaluation stage may read it. Nothing
  that produces a verdict can see it, which is what makes a scorecard a measurement
  rather than a restatement.
- **Every output is citable.** A verdict with no clause behind it is held, not sent.
  An answer not in the approved library does not go out.
- **The findings can fail.** The forecasting agent ships tests designed to disprove
  its own conclusions, and reports when one does.

All three run on synthetic data generated from a fixed seed, so every figure above
reproduces exactly. The faults in the data are ones I built in deliberately. On real
data the levels differ — what transfers is the method.

---

📧 dchoudhury.oct@gmail.com
