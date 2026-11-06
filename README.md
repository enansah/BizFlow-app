# BizFlow-app
An inventory management app that is used to organise stock, make sales, manage staff duties, contact suppliers of specific stocks and the more.

I'm building BizFlow for small shops here in Ghana: provision stores, cosmetics shops, chemical shops. A lot of them still write sales in a notebook and only find out at the end of the month that stock or money has gone missing.

The idea is simple. Staff sell from a cheap Android phone, even when there's no internet. The owner can see what was sold, who sold it, what's running low and who owes the shop money, from anywhere. Customers pay with cash or MoMo.

## Where things are

- `web/` is the app the shops will use (React).
- `server/` handles accounts, syncing, SMS and Paystack payments (Node).
- `docs/` has the prototype documentation, the clickable prototype and the logo.

## How I work on it

`main` only gets work that has been tested. Everyday work goes into `develop`, and each feature gets its own branch off it, like `feature/selling` or `feature/momo-prompts`. The full steps are in [CONTRIBUTING.md](CONTRIBUTING.md).

## Where it's at

For now BizFlow is a clickable prototype. Building the real app is next.
