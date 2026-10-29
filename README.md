# SignalRoom

SignalRoom is a small, runnable prototype for evidence-driven production incident investigation.

## Run

No dependencies or API keys are required. From this folder, run:

    node serve.js

Then open `http://localhost:3000` (or the port printed by the server). The app is plain HTML, CSS, and JavaScript.

## How to demo

1. Scroll to **Replay an incident. Get a plan.**
2. Keep the prefilled representative case and click **Analyze incident**.
3. Show the ranked hypotheses, supporting/contradicting evidence, reconstructed timeline, and recommended first move.
4. Click **Load invalid case**, then **Analyze incident**. The app should reject the packet because it lacks a specific summary and enough signals.

## Sample expected output

The representative packet ranks **Upstream inventory dependency is timing out** first, at approximately **92% lead confidence**, and recommends checking inventory latency/saturation against the checkout-api request timeout. The result is a lead for investigation, not autonomous remediation.

## Scope and boundaries

- Implemented: problem framing, approach rationale, input validation, deterministic ranking, evidence labels, timeline reconstruction, responsive UI.
- Mocked: incident data and the “AI” analysis logic. The rules are intentionally transparent and local.
- Deferred: authenticated log/metric/deploy connectors, persistent incident history, model evaluation, permissions, and real remediation actions.

## Time and AI note

Estimated build time: about 2 hours. AI was used to help structure the page, draft UI copy, and review edge cases. I checked the output by reading the source, exercising both the representative and invalid paths, and verifying that the ranking is generated from the entered signals rather than a static screenshot. I reused the existing workspace only as a starting shell; the prior portfolio content was replaced with this focused submission prototype.

## Next investigation

I would run a replay study with responders using resolved incidents. The key decision is whether the evidence-linked brief reduces time-to-first-useful-action while keeping users able to explain and challenge the top hypothesis.
