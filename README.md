# Life Manager — Pay with PayPal, Managed by AI

PayPal AI Hackathon prototype. Life Manager is Anicca's autonomous AI manager
(live product: https://aniccaai.com/maritime — $29/month, 7-day free trial).
This prototype adds the money loop: subscribe via **PayPal Sandbox**, and on
capture the AI manager provisions the workspace and generates a personal
onboarding brief.

## Run it
Hosted demo: https://daisuke134.github.io/life-manager-paypal-ai/

Or locally: serve this folder with any static server, e.g.
`python3 -m http.server 8000` then open http://localhost:8000

## How it works
- PayPal JS SDK (Sandbox, `client-id=sb`) renders the checkout button.
- `actions.order.create` creates a $29.00 order; `actions.order.capture`
  captures it after buyer approval — the standard PayPal Orders flow.
- On capture, the brief generator composes the onboarding brief from the
  order data (payer name, order ID, time of day) and displays it.

## AI tools (honest disclosure)
The brief generator in this prototype is an in-browser deterministic
template-composition module driven by order data. It stands in for Life
Manager's production LLM-based manager. The PayPal Sandbox integration is
fully functional; no real money moves.

## License
MIT — see LICENSE.
