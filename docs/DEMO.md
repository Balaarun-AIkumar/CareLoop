# Local demo

Run `python -m scheduler serve --gemini`, then open http://127.0.0.1:8000.

1. Use the synthetic patient and appointment scenario configured by the app, then choose one of the displayed slots.
2. At the booking preview, send an ambiguous reply such as “Sounds interesting.” Verify that the appointment remains pending. Then confirm explicitly and inspect the committed receipt.
3. Open **Improvement lab**, select **Initial policy comparison**, and start the loop. Review the baseline failures, generated changes, replay, validation, and promotion decision in **Experiment log**.
4. Expand **soft afternoon** and compare the selected slot before and after the policy change. Finish on the scores and active-policy status.

The recorded experiment reports training moving from 28/32 to 32/32 and validation from 10/12 to 12/12, with no regressed checks. It used one live Gemini repair request and 100 cached interpretations. This adapts prompts and policy settings; it does not retrain the model. The validation cases are regression checks after development review.
