# Atchaar — Atcaar e monate!

A responsive, single-page demo storefront for an Atchaar South African pickle and atchaar business. The site is plain HTML, CSS and JavaScript and has no build step or package dependencies.

## Run locally

Open `index.html` in a current browser. An internet connection is needed for the hosted Unsplash photography and Google Fonts; the storefront itself does not depend on a third-party JavaScript library.

## Deploy to Render

This is a static site and needs no server process or build step. The included `render.yaml` configures a Render Static Site that publishes the repository root. To deploy, push the repository to GitHub, then in Render choose **New > Blueprint** and connect `Cynthia35/Atchaar`; alternatively, create a **Static Site** for that repository and use the `main` branch, repository root as the root directory, `echo "No build required"` as the build command, and `.` as the publish directory. Render will serve `index.html` and can automatically redeploy on pushes.

The `.env.example` file is documentation only; this static storefront does not use server-side environment variables.

## Customise before launch

- Edit `PRODUCTS` in the script in `Index.html` to change product names, descriptions, images, spice levels, sample availability, review ratings and size/price options.
- Replace all sample prices, stock counts, placeholder business/about copy, contact information, delivery details, and example reviews with confirmed business information.
- Update `SHOP_CONFIG` to set the delivery fee, free-delivery threshold and the WhatsApp phone number in international format. The contact and social controls intentionally identify themselves as placeholders until configured.
- Product prices are examples only, are displayed in ZAR, and must be confirmed before launch.

## Demo-only behaviour and production integrations

Cart contents and browser-submitted demo reviews are stored in the visitor's local storage. Newsletter and contact forms only validate and show a local success message. Demo checkout collects details in the browser, creates a clearly labelled reference, clears the local basket and does **not** send customer details, create a server-side order, or accept/verify payment. It must not be represented as a real order or paid transaction.

For a live shop, add a server-side order API and persistent database, validate product IDs, prices, stock and quantities on the server, and calculate totals there. Initiate payment through PayFast or Yoco from the server using server-only credentials, verify provider callbacks/webhooks server-side, and mark an order paid only after successful verification. Never accept card details in this static page or expose secret keys in browser code. Add server-backed contact/newsletter handling and moderated, preferably verified-purchase, reviews before production.

`.env.example` lists placeholder names for a future server integration. This static demo does not load environment variables; do not put real credentials in `Index.html` or any `VITE_`/browser-exposed variable.
