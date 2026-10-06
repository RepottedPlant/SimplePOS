# Simple POS

Simple POS is a free, lightweight point-of-sale system for pop-ups, small vendors, markets, and events. It runs in the browser, requires no account or backend, and stores your products, orders, sales, branding, and payment details locally on the device and browser you are using.

Made freely available as an open initiative under **Utpatti — The Creative Collective**.

**Live version:** https://repottedplant.github.io/SimplePOS/

---

## Features

### Point of Sale

- Add products to an order with a single tap or click
- Tap the same product again to increase quantity
- Remove individual items using the minus button
- View the current order total in real time
- Clear an order before placing it
- Assign a daily sequential order number to every order
- Display the next order number while taking an order
- Order numbers reset each day
- Choose a payment type before placing an order:
  - Cash
  - Card
  - Bank Transfer
  - QR Payment
- Tapping **Place Order** opens a payment checkout step for the selected payment type
- Orders are only added to Sales after payment is confirmed
- Cash checkout lets the user enter the amount received and automatically calculates change
- Cash checkout includes **Clear** and **Exact Amount** shortcuts
- QR checkout shows the saved payment QR code
- Bank Transfer checkout shows the saved transfer details
- Card checkout shows the amount due while payment is completed using an external card terminal

### Product Categories

- Products can be grouped into categories
- Category buttons are generated automatically from product data
- Includes an **All Products** view
- Categories disappear automatically when no products use them
- Categories can be reordered from **Customize → Products & Categories**
- **All Products** always remains first

### Product Management

Products can be added, edited, or removed from **Customize → Products & Categories**.

Each product can contain:

- Product name
- Price
- Category
- Optional custom accent color
- Optional menu note

If a product does not have a custom accent color, it uses the POS primary brand color.

Menu notes can be used for short labels such as:

- Today's Special
- New
- Limited
- Best Seller

### CSV Product Import

Products can be imported in bulk using a CSV file.

Required columns:

- `Product name`
- `Price`
- `Category`

Optional columns:

- `Color`
- `Note`

Example:

```csv
Product name,Price,Category,Color,Note
Americano,700,Coffee,,
Iced Milo Dino,1000,Coffee,#FF5A2F,Today's Special
T-Shirt,2500,Clothing,#2B6E4F,Featured
```

`Color` should be a hex color value such as `#FF5A2F`. Leave it blank to use the POS primary brand color.

The POS also includes a downloadable CSV template.

When importing, users can either:

- Add or update products while keeping existing products
- Replace the current product list entirely

### Branding and Appearance

Simple POS can be customized to match a business or event brand.

Under **Customize → General & Branding**, users can configure:

- Business / POS name
- Currency
- Brand logo
- Ready-made themes
- Custom primary brand color
- Custom secondary / CTA color
- Light mode
- Dark mode
- System appearance mode

Core backgrounds, text, borders, and form controls are managed automatically so custom brand colors remain readable.

#### Logo recommendations

Horizontal or wordmark logos work best in the Simple POS header.

Recommended:

- Approximately a **4:1 aspect ratio**
- Example size: **800 × 200 px**
- Transparent PNG where possible

Square or tall logos are supported, but they will appear smaller in the header.

### Configuration Backup and Transfer

The POS setup can be exported as a JSON configuration file and imported on another device or browser.

The configuration file can include:

- Business / POS name
- Currency settings
- Selected theme and appearance mode
- Brand colors
- Products
- Product accent colors
- Product menu notes
- Category order
- Payment information
- Optional brand logo
- Optional payment QR code

Sales history and the current cart are not included in configuration exports.

Users can choose whether to include the logo and payment QR when exporting. Images are embedded directly inside the JSON file, which makes the file larger but keeps the setup in a single file.

When importing a configuration:

- Current products and configuration are replaced
- Existing sales history is preserved
- The current cart is cleared
- If the imported file does not contain a logo or QR code, the logo and QR already stored on the device are preserved

CSV is intended for product import and editing, while JSON is intended for transferring or backing up the complete POS setup.

### Sales Dashboard

The **Sales** section opens on the current day by default.

It shows:

- Revenue for the selected day
- Number of orders
- Number of open orders
- Number of items sold
- Product sales breakdown
- Order history
- Order numbers
- Order completion status
- Payment type for new orders
- Daily starting cash
- Cash sales
- Expected cash in the drawer
- The next order number for the current day

Users can also review earlier sales using:

- A calendar/date picker
- Previous-day and next-day controls
- A shortcut back to **Today**

Orders can be marked as **Completed** once they have been prepared or handed over to the customer.

Completed orders can also be reopened if they were marked accidentally.

### Sales Export

Sales can be exported as a CSV for whichever day is currently selected in the Sales section.

This means a user can return later and export a previous day's sales if they forgot to do it at the end of the day.

The export includes information such as:

- Date
- Order number
- Order status
- Payment type
- Time
- Product
- Category
- Quantity
- Unit price
- Line total
- Order total
- Currency
- A daily summary including starting cash, cash sales, and expected cash

Older orders created before payment-type tracking was added remain compatible; their payment type may simply be blank or shown as not recorded.

### Payment Checkout and Display

Payment is now part of the order flow. After choosing a payment type and tapping **Place Order**, Simple POS opens a checkout modal for that payment method.

- **Cash** — enter the amount received and Simple POS calculates the change
- **QR Payment** — shows the saved payment QR code
- **Bank Transfer** — shows the saved transfer details
- **Card** — shows the amount due while the payment is completed on an external card terminal

The order is only added to Sales after **Confirm Payment** is pressed.

A dedicated **Payment** section is still available when payment details need to be shown to a customer outside of an active order.

Users can configure:

- Payment QR code
- Bank name
- Account name
- Account number
- Branch
- Transfer instructions or payment notes

The saved QR code and bank details are reused automatically during checkout, while the standalone Payment section makes it possible to show the same information without placing an order.

### First-Time Welcome

New users are shown a short welcome message explaining how Simple POS works before they begin setup.

It explains that:

- No account is required
- There is no cloud sync
- POS data is stored in the current browser on the current device
- Another device or browser will have separate data
- Clearing browser/site data can remove locally stored POS data
- Sales CSV and JSON configuration exports should be used for records and backups

Existing users are not shown the first-time welcome when upgrading to a newer version.

### What's New

Simple POS can display a **What's New** message after a new release.

User-facing release notes are stored in a separate `updates.json` file. When the latest update ID changes, users who have not seen that release are shown a short summary of the new features the next time they open the hosted app.

The acknowledgement is stored locally in the browser and is not included in configuration exports.

New users are not shown the Welcome modal and the What's New modal back-to-back; the current release is marked as seen after first-time onboarding.

### Currency Settings

Simple POS supports several built-in currencies, including:

- LKR
- USD
- EUR
- GBP
- AUD
- CAD
- INR
- SGD
- AED
- JPY

A custom currency label can also be used.

### Built-in How to Use Guide

Simple POS includes a **How to Use** section inside the app.

It covers:

- First-time setup
- Branding and appearance
- Taking orders
- Using the POS on a tablet, phone, or computer
- Products and categories
- CSV product import
- Sales dashboard
- Previous-day sales
- Payment checkout and payment display
- Configuration backup and transfer
- Data storage and backups
- Current limitations

---

## Customize Menu

The Customize section is split into four areas.

### General & Branding

Used for:

- Business / POS name
- Currency
- Brand logo
- Themes and appearance
- Custom brand colors
- Configuration export and import

### Products & Categories

Used for:

- Adding and editing products
- Product accent colors
- Product menu notes
- Category ordering
- CSV product import
- Product management

### Payment Information

Used for:

- Payment QR code
- Bank transfer details
- Transfer notes or instructions

### Danger Zone

Contains destructive actions such as resetting the entire POS.

The Danger Zone is visually marked in red and is not required for normal setup or daily operation.

---

## How It Works

Simple POS is a static web application.

There is:

- No backend
- No custom database
- No login system
- No cloud sync
- No external POS service required

POS data is stored using the browser's `localStorage`.

This includes:

- Business / POS name
- Currency settings
- Brand logo
- Theme and appearance settings
- Products
- Product accent colors
- Product menu notes
- Category order
- Current cart
- Sales history
- Order completion status
- Payment type for supported orders
- Daily starting cash
- Payment QR code
- Bank transfer details

Simple POS also stores small local flags separately for first-time onboarding and the last **What's New** release seen by that browser.

---

## Running the POS

### Option 1 — Hosted version / GitHub Pages

The easiest way to use Simple POS on a tablet or phone is the hosted version:

https://repottedplant.github.io/SimplePOS/

If hosting your own copy:

1. Add `index.html` and `updates.json` to the same GitHub repository.
2. Enable GitHub Pages for the repository.
3. Open the generated GitHub Pages URL in your browser.
4. On iPad or iPhone, open the page in Safari and use **Add to Home Screen** for a more app-like experience.

The hosted version is recommended because the **What's New** feature loads `updates.json` using `fetch()`. Browsers may block that request when `index.html` is opened directly from the local filesystem.

### Option 2 — Desktop Browser

The HTML file can also be opened directly in a desktop browser for testing or local use.

Core POS functions will still work, but features that fetch repository files such as `updates.json` may not work when running from `file://`.

---

## First-Time Setup

1. Open **Customize**.
2. Under **General & Branding**, set the business / POS name and currency.
3. Optionally upload a logo and choose a theme or custom brand colors.
4. Choose Light, Dark, or System appearance.
5. Under **Products & Categories**, add products manually or import them from CSV.
6. Arrange categories in the order you want them displayed.
7. Optionally give individual products an accent color or short menu note.
8. Under **Payment Information**, add a payment QR code and bank details if required.
9. Return to **POS** and begin taking orders.

If you already have a Simple POS JSON configuration file, you can import it from **Customize → General & Branding → Configuration Backup & Transfer** to skip most of the manual setup.

---

## Typical Order Workflow

1. Select a category or use **All Products**.
2. Tap products to add them to the current order.
3. Use the minus button if an item was added accidentally.
4. Confirm the total.
5. Choose the payment type:
   - Cash
   - Card
   - Bank Transfer
   - QR Payment
6. Tap **Place Order**.
7. Complete the payment step shown in the checkout modal.
   - For cash, enter the amount received to calculate the change.
   - For QR or bank transfer, use the saved payment details shown on screen.
   - For card, complete the payment on the external terminal.
8. Tap **Confirm Payment**. The order is only added to Sales after this step.
9. Call out the displayed order number when the order is ready.
10. Open **Sales** and mark the order as **Completed**.

---

## Data Storage and Backups

All POS data is stored locally on the device and browser being used.

This means:

- Refreshing or closing the page normally does **not** remove the data.
- Different devices have separate data.
- Different browser profiles have separate data.
- A different website or domain will have separate local storage.
- Clearing browser or site data can remove the POS data.
- There is currently no automatic cloud backup.

For important events or sales periods, it is recommended to export sales CSV files regularly.

If you forget to export at the end of the day, open **Sales**, choose the earlier date, and export that day's CSV later.

Use the separate JSON configuration export to back up or transfer the POS setup itself.

### Sales CSV vs Configuration JSON

**Sales CSV**

- Contains sales information for the selected day
- Includes payment type where recorded
- Useful for reporting, records, and external analysis

**Configuration JSON**

- Contains the POS setup
- Useful for moving a setup to another device or browser
- Can optionally include the brand logo and payment QR
- Does not contain sales history
- Does not contain What's New or onboarding acknowledgement state

Simple POS is intended for lightweight use and should not be treated as a replacement for a full accounting system or cloud-backed commercial POS.

---

## Privacy

Simple POS does not require an account and does not send POS data to a custom backend.

When hosted as a static site, order and configuration data remain in the browser's local storage.

The hosting provider will still handle the normal web requests required to serve the page and files such as `updates.json`.

---

## Limitations

Simple POS currently does not include:

- Multi-device syncing
- Cloud backup
- User accounts or staff permissions
- Stock / inventory management
- Integrated card payments
- Receipt printing
- Tax calculation
- Refund workflows
- Customer database
- Kitchen / preparation screen
- Automatic online backups

The project is intentionally kept simple so it remains useful for small pop-ups, markets, events, and temporary sales setups.

---

## Project Structure

The project remains intentionally lightweight.

```text
SimplePOS/
├── index.html
├── updates.json
├── README.md
└── LICENSE
```

`index.html` contains the application HTML, CSS, and JavaScript.

`updates.json` contains user-facing release notes used by the **What's New** modal.

No build process is required.

---

## Contributing

Suggestions, improvements, bug reports, and contributions are welcome.

If you make changes that could be useful to other small vendors or pop-up operators, feel free to open an issue or pull request.

When adding a user-facing feature, consider adding a short entry to `updates.json` so existing users can discover it after the next release.

---

## License

This project is licensed under the **GNU General Public License v3.0 (GPL-3.0)**.

You are free to use, study, modify, and redistribute the software under the terms of the GPL v3. If you distribute modified versions of the project, those versions must also be made available under the GPL v3 with their corresponding source code.

See the [`LICENSE`](LICENSE) file for the full license text.

---

## Initiative

Simple POS is made freely available as an open initiative under **Utpatti — The Creative Collective**.
