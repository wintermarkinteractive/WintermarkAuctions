# Changelog

## 1.0.0 - 2026-11-25
First public release. Everything from 0.1.0-0.3.0, plus:

- Menu buttons no longer show vanilla item stats (e.g. attack damage on the Combat category sword).

## 0.3.0 (2026-11-25)
- **Expiry + collection box:** listings end after `listing-hours`; expired, taken-back (full inventory), staff-removed and overflow items wait in `/ah collect` (barrel button in the menu). Click to take one, or "Take everything". Join reminder when items are waiting.
- **Tax + fees:** `listing-fee-percent` (paid when listing, not refunded) and `sales-tax-percent` (taken from the seller's payout).
- **Limits:** `max-listings` (default 5), VIP limits with `wintermark.ah.limit.<n>`, `min-price` / `max-price`.
- **Buying with a full inventory** now works: the item goes to your collection box.
- **Offline sale summary:** sellers who were offline get a list of what sold (and the total) when they join.
- **Staff:** shift + right-click a listing to remove it; the item goes to the seller's collection box.

## 0.2.0 (2026-11-25)
- **Bottom bar:** category filter (All, Blocks, Tools, Combat, Food, Potions & Books, Misc; left/right-click to cycle), sort (newest, cheapest, most expensive), search, "My listings" switch, balance.
- **Search** by item name through a native text-input dialog (left-click the sign; right-click clears). Also `/ah search <text>`.
- **My listings:** `/ah my` or the chest button; click one to take it back.
- Filters, sort and page are remembered when you open a confirm screen and come back.
- "No listings match" screen when a filter finds nothing.

## 0.1.0 (2026-11-25)
- `/ah sell <price>` lists the item in your hand (abbreviations work). The item is taken from your inventory before the listing exists (anti-dupe).
- `/ah` menu: 45 listings per page (newest first) with price, seller and time left, pages, balance and info buttons.
- Click a listing → confirm screen → money moves, item to the buyer (needs a free slot), seller paid instantly (also when offline; online sellers get a message).
- Click your own listing to take it back.
- A listing is removed from the list before any money moves, so it can only be sold once.
- SQLite storage (`auctions.db`) with status ACTIVE / SOLD / CANCELLED; items stored with `ItemStack.serializeAsBytes()`.
- Works with Wintermark Economy (history type AUCTION) or any Vault economy.
