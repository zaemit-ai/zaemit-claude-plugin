# Zaemit for Claude

Zaemit is an AI web production service that takes your website from building to data management and day-to-day operations, all in one flow. This plugin connects Zaemit to Claude so you can do it all by chatting.

## What it does

Building your site starts with one sentence. Tell Claude: "Make a homepage for my pottery studio in Seongsu. Warm and calm, with class info, directions and a contact form." Zaemit designs the pages, writes the copy, fills in the photos and sets up the header, footer and menu. Your site goes live at its own address right away, with AI-search optimization (AEO/GEO) built in.

Building is only the beginning. Keep talking to Claude to run your site. Just say "add a board" or "set up reservations", and the feature is ready on your site with its data and admin screen. Everything below is available through your conversation with Claude:

- Page editing: headlines, sections, backgrounds, page names and menus, with every change reversible.
- Inquiry forms: add forms and fields, check incoming inquiries, reply and track their status.
- Boards: open a notice board, write, edit or delete posts, and place the board on any page.
- Reservations: bookable services and schedules, see new bookings and confirm them.
- Shop: products and categories, prices and display, order status, review replies and coupons.
- Contests and events: open a contest and move entries through review stages, manage participants, check-in, registrations and session programs.
- Promotion and insights: SEO, popups and visitor statistics.

## What's in the plugin

- **The Zaemit connector** (`https://zaemit.ai/mcp/claude`), the same server as the Zaemit connector in the Claude directory.
- **Skills** that guide Claude through Zaemit work: which tool fits a request, the order of steps, and how confirmations work.

| Skill | Used when you want to |
|---|---|
| zaemit-getting-started | start working with a connected site, turn on a feature, or handle a confirmation |
| zaemit-build-site | build a new site or a new page, or redesign a whole page |
| zaemit-site-pages | edit pages, menus, header and footer, SEO, popups or site contacts, check visitors or undo a change |
| zaemit-boards-inquiries | run boards and inquiry forms, and answer submissions |
| zaemit-commerce | run a shop: products, orders, reviews and coupons |
| zaemit-reservations | take reservations: time slots, opening hours, a booking screen and confirming bookings |
| zaemit-contests | run a contest or award program: entries, judging and results |
| zaemit-events | run networking events and check-in, paid registrations, conference sessions and speakers, and event budgets |

## How to use it

1. You need a Zaemit account (sign up at https://zaemit.ai). You don't need a site beforehand.
2. Add the plugin, then connect the Zaemit connector. On claude.ai and in Cowork it is on the plugin's **Connectors** tab; Claude Code connects to it with the plugin.
3. Sign in to Zaemit. On the consent screen, create a new site or pick an existing one. Each connection works on one site.
4. Ask in plain language, for example:
   - "Make a homepage for my cafe. It's called 'Haru Cafe', in Seongsu, Seoul, with a warm and cozy mood. Include a menu introduction, directions and a contact form."
   - "Create separate pages for the menu and the directions, and link them from the top menu."
   - "Add a notice board to my home page."

Changes that delete or revert content run only after you confirm them. Some features depend on your Zaemit plan.

## Data

- The plugin sends your requests to the Zaemit server at `zaemit.ai` through the connector, on behalf of the signed-in Zaemit account, for the connected site only.
- Responses contain the site's content and settings. Names, phone numbers, emails and addresses of members and customers are masked unless you allowed raw access when connecting.
- When Zaemit fills in photos, it uses the Zaemit photo library and stock photos from Unsplash and Lummi, and copies them into your site's storage. Photos of people may be AI-generated and use Zaemit credits.
- The plugin itself stores nothing and contains no secrets. Zaemit handles the data it receives under its [privacy policy](https://zaemit.ai/privacy-policy).

## Support

Zaemit is operated by Weven Co., Ltd.

- Customer center: https://zaemit.ai/customer-center (phone +82-2-6951-1136, weekdays 09:00-18:00, closed on weekends and public holidays)
- Privacy policy: https://zaemit.ai/privacy-policy
- Terms of service: https://zaemit.ai/terms-of-service

The customer center, privacy policy and terms are in Korean.

## License

MIT. See [LICENSE](LICENSE).
