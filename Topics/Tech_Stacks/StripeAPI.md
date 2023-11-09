# Setting Up Stripe API in a JS Environment

## 1. Introduction to Stripe
- Watch the [Introduction Video](https://www.youtube.com/watch?v=7edR32QVp_A).
- Explore the [Stripe API documentation](https://stripe.com/docs/development/get-started).

## 2. Create a Stripe Account
- [Sign up](https://stripe.com/docs/development/get-started) for a Stripe account.

## 3. Obtain API Keys
- In your [Stripe Dashboard](https://dashboard.stripe.com/), go to "Developers" > "API keys" to find your keys.

## 4. Install Stripe Library
- In your Node.js project, install the Stripe npm package:
  ```bash
      npm install stripe
  ```

## 5. Implement Payment Integration (React.js)
- Install the Stripe React library:
  ```bash
      npm install @stripe/react-stripe-js @stripe/stripe-js
  ```
- Follow the guide on [Accept a payment](https://stripe.com/docs/development/quickstart) for React.

## 6. Handle Webhook Events (Node.js)
- Create a server-side route using Express and the Stripe package to handle webhook events.

## 7. Implement Subscription Logic (If Needed)
- Follow the [Stripe Subscriptions guide](https://stripe.com/docs/billing/subscriptions/overview).

## 8. Secure Your Integration
- Ensure your React.js app uses HTTPS.
- Keep API keys secure; never expose them on the client side.

## 9. Test Transactions
- Simulate transactions using [Stripe test card numbers](https://stripe.com/docs/testing).

## 10. Documentation
- Document your integration, including setup instructions, API usage, and error handling.

## 11. Set Up Stripe CLI
- Install the [Stripe CLI](https://stripe.com/docs/development/quickstart#set-up-stripe-cli).

## 12. Authenticate Stripe CLI
- Run `stripe login` in the command line and follow the authentication process.

## 13. Confirm Setup
- Use the Stripe CLI to create a sample product and price to confirm setup.

## 14. Install Node.js SDK
- Initialize Node.js in your project and install the Stripe Node.js server-side SDK:
  ```bash
      npm init
      npm install stripe --save
  ```

## 15. Run First SDK Request
- Create a subscription product and attach a price using the Node.js SDK. Save the following code in a file, e.g., `create_price.js`:
  ```javascript
      const stripe = require('stripe')('sk_test_Hrs6SAopgFPF0bZXSN3f6ELN');

      stripe.products.create({
        name: 'Starter Subscription',
        description: '$12/Month subscription',
      }).then(product => {
        stripe.prices.create({
          unit_amount: 1200,
          currency: 'usd',
          recurring: {
            interval: 'month',
          },
          product: product.id,
        }).then(price => {
          console.log('Success! Product ID: ' + product.id);
          console.log('Success! Price ID: ' + price.id);
        });
      });
  ```
- Run the following command:
  ```bash
      node create_price.js
  ```
- Save the product and price identifiers for future use.

## 16. Save Identifiers
- Save identifiers generated during setup for future use.

## 17. Explore Further
- Refer to the official [Stripe documentation](https://stripe.com/docs) for in-depth information.
