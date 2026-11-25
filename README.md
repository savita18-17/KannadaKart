# KannadaKart — ನಿಮ್ಮ ಊರಿನ ವ್ಯಾಪಾರ, ಈಗ ನಿಮ್ಮ ಕೈಯಲ್ಲಿ

**KannadaKart** is a Kannada-first rural e-commerce platform built for Karnataka, connecting farmers, rural artisans, women weaver collectives, and village shopkeepers directly with buyers.

## Key Capabilities

1. **Kannada-First Bilingual Experience (`kn` default + `en`)**:
   - Full UI, product catalogs, notifications, checkout, and AI responses in Kannada and English.
2. **Kannada Voice Product Search (`kn-IN` / `en-IN`)**:
   - Web Speech API integration inside `/marketplace` supporting natural queries such as `"ಅಕ್ಕಿ ತೋರಿಸು"`, `"ನೂರು ರೂಪಾಯಿಗಿಂತ ಕಡಿಮೆ ಬೆಲೆಯ ವಸ್ತುಗಳನ್ನು ತೋರಿಸು"`, and `"ಮಣ್ಣಿನ ಪಾತ್ರೆಗಳು ಹುಡುಕು"`.
3. **ChatGPT / WhatsApp-Style Kannada AI Seller Assistant (`/seller/assistant`)**:
   - Full conversational workspace with a **10-action horizontal shortcut toolbar** directly above the message composer and microphone.
   - Voice & text command parsing with mandatory confirmation cards before any store mutation.
   - Real-time **two-way synchronization** across the Assistant, Seller Dashboard, Inventory, Discounts, and Marketplace.
4. **Photo-to-Listing Assistant (`/seller/photo-listing`)**:
   - Demo product image analysis with strict non-perishable eligibility enforcement (rejecting fresh produce, dairy, meat/fish, medicines, and expiry-sensitive goods).
5. **Complete E-Commerce & Order Workflow**:
   - Cart, delivery threshold calculation, Demo UPI / Demo COD checkout, buyer order tracking & cancellation, and seller order acceptance/fulfillment transitions.
6. **PWA Ready**:
   - Web App Manifest, Workbox service worker (`vite-plugin-pwa`), app icons, offline shell indicator, and in-app install prompt.

## Running Locally in VS Code

No paid API keys or Supabase credentials are required. Everything runs in full Demo Mode with `localStorage` persistence.

```bash
npm install
npm run dev
```

Open `http://localhost:3000`.

### Demo Credentials
- **Demo OTP**: `123456` (Simulated locally — no SMS or email is sent)
- **Quick Demo Accounts**: One-click **Demo Buyer** and **Demo Seller** buttons on `/login`
- **Demo Payments**: Checkout uses simulated UPI/COD without collecting real PINs or banking credentials.

## Project Structure

- `src/components/` — Reusable UI components (`common`, `marketplace`, `assistant`)
- `src/pages/` — Public, Buyer, and Seller route views
- `src/services/` — Service interfaces, `mock/` implementations, and `supabase/` placeholders
- `src/context/` — Centralized `LanguageContext` and synchronized `AppStateContext`
- `src/hooks/` — `useVoiceInput`, `useTextToSpeech`, `usePWAInstall`, `useOnlineStatus`
- `src/data/` — Karnataka categories, sellers, products, orders, and translations
- `src/types/` — TypeScript domain models and service contracts
- `src/utils/` — Formatters, validators, CSV export, speech helpers, eligibility checks
- `docs/DATABASE_SCHEMA.md` — Supabase PostgreSQL schema and Row Level Security (RLS) policies
