# DosaCorner

Production-style South Indian restaurant ordering frontend.

- Exactly 245 dishes with names, prices, ratings and Veg/Non-Veg labels
- Category and dietary filtering
- Search
- Animated cards and floating food effects
- Cart with quantity controls and browser persistence
- Checkout and payment-selection UI
- Responsive mobile layout
- Real hero image asset
- Jenkins pipeline for validation, packaging, deployment and artifact archiving

## Local run
`python3 -m http.server 8080`

## Jenkins deployment
The Jenkinsfile deploys the site to `$HOME/dosacorner-site`.

Payment is a frontend checkout UI only; connect a real payment gateway/backend before accepting real payments.


## Food photography
Each of the 245 menu records is mapped to its own dish-specific AI food-photography URL, so the cards display real-looking dish photographs rather than emoji placeholders. Internet access is required when the browser first loads those remote images.
