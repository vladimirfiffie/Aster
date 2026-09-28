# Aster

A full-featured Material 3 e-commerce app built entirely in Flutter — no web views or embedded sites, just native mobile UI components and responsive interactions.

> **Prerelease:** This is a demo/test build. Checkout is simulated: no real payment is taken, and no payment data is collected or stored.

---

## At a Glance

Aster is a complete shopping application designed to look and feel like a modern, top-tier retail app.

- **Complete Shopping Experience:** Browse live products, filter by category or price, manage a cart, redeem gift cards, and step through a validated checkout flow.
- **Offline-First:** Your cart, saved items, past orders, and recently viewed products are persisted locally and load instantly, even without an internet connection.
- **Native & Accessible:** Full dark mode and AMOLED-black themes, device biometrics at checkout, subtle haptic feedback, and screen-reader support.
- **Smart Order Tracking:** Place an order and track its status as it progresses from processing to delivery directly from your account history.

---

## Screenshots

| Home & Feed | Product & Details | Interactive Bag |
|:---:|:---:|:---:|
| <img src="" width="240" alt="Aster Home Screen"> | <img src="docs/screenshots/product.png" width="240" alt="Aster Product Detail Screen"> | <img src="" width="240" alt="Aster Bag Screen"> |
| <sub>Promo carousel & deals</sub> | <sub>Price history & reviews</sub> | <sub>Free shipping & promotions</sub> |

| Checkout Stepper | Live Orders Tracker | AMOLED Black Theme |
|:---:|:---:|:---:|
| <img src="" width="240" alt="Aster Checkout Screen"> | <img src="" width="240" alt="Aster Orders Screen"> | <img src="" width="240" alt="Aster AMOLED Dark Mode"> |
| <sub>Biometrics & address forms</sub> | <sub>Real-time status stages</sub> | <sub>True-black UI surfaces</sub> |

---

## App Features

| Area | Details |
| --- | --- |
| **Welcome** | Sign in, create a local account, or browse as a guest. Guest sessions are remembered across restarts. |
| **For You** | Live order status tracking, delivery countdowns, price-drop alerts, and free-shipping progress. |
| **Home** | Auto-advancing promotional banner, category tiles, new arrivals, deals, and pull-to-refresh. |
| **Shop** | Catalog organized into six categories, grid/list view toggle, and filter/sort sheets for price, rating, and stock. |
| **Search** | Instant search results with search history and trending search terms. |
| **Product** | Image gallery with pinch-to-zoom, size guides, specification tables, customer reviews, and historical price tracking. |
| **Brand** | View an entire brand catalog, average rating, and sale inventory. |
| **Bag** | Variant selection, swipe-to-delete with undo, promo-code entry, and live order-total calculations. |
| **Checkout** | Three-step checkout with address/card validation, Luhn card validation, delivery speeds, gift wrapping, and store credit. |
| **Orders** | Delivery progress tracking, order cancellation before dispatch, returns, and downloadable receipts. |
| **Saved Items** | Organize products into custom named lists and bulk-add items to the bag. |
| **Reviews** | Verified-buyer reviews with up to four photos, rating breakdowns, and user edit history. |
| **Profile** | Recent order summaries, dark/light/AMOLED theme settings, eight color schemes, and notification preferences. |

---

## Device Integration

| Feature | Implementation |
| --- | --- |
| **Haptics** | Custom tactile feedback across four distinct channels with three intensity levels. |
| **Notifications** | Scheduled local notifications for order confirmations, shipping updates, and delivery alerts. |
| **Biometrics** | Opt-in fingerprint / Face ID verification before finalizing payments. |
| **Accessibility** | Screen-reader labels, high-contrast text, and tap targets validated through automated tests. |
| **Large Screens** | Adaptive layouts with navigation rails on tablets and foldables at 840dp+. |
| **Platform Native** | Automatically adapts UI components between Material on Android and Cupertino styling on iOS. |
| **Localization** | English and Spanish support, including locale-aware date and currency formatting. |

---

## Tech Stack & Architecture

- **Framework:** Flutter 3.44 / Dart 3.12 with Material 3
- **State Management:** `flutter_riverpod 3` with custom persistence seams for seamless unit testing
- **Routing:** `go_router` with `StatefulShellRoute.indexedStack` to preserve state across bottom tabs
- **Networking & Caching:** `http` for feed consumption, paired with `cached_network_image` and loading skeletons
- **Security & Authentication:** Local PBKDF2-HMAC-SHA256 password hashing via `crypto`; biometric authentication via `local_auth`
- **Testing:** 411+ unit/widget tests covering business logic, catalog edge cases, locale formatting, and four end-to-end integration tests

### Project Structure

```text
lib/
├── core/         # Theme, router, formatters, enum lookups
├── data/         # Models and repositories
├── state/        # Riverpod providers (cart, favorites, orders, settings)
├── features/     # Feature-first architecture (one folder per screen)
├── shared/       # Reusable UI widgets across features
└── l10n/         # App localization files (English & Spanish ARB)
