# Simple POS

Simple POS is a free, lightweight point-of-sale system for pop-ups, small vendors, markets, and events. It runs entirely in the browser, requires no account or backend, and stores your products, orders, sales, and payment details locally on your device.

Made freely available as an open initiative under **Utpatti - The Creative Collective**.

## Features

### Point of Sale
- Add products to an order with a single tap or click
- Remove individual items using the minus button
- View the current order total in real time
- Clear an order before placing it
- Assign a daily sequential order number to every order
- Display the next order number while taking an order
- Order numbers reset each day

### Product Categories
- Products can be grouped into categories
- Category buttons are generated automatically from product data
- Includes an **All Products** view
- Categories disappear automatically when no products use them

### Product Management
Products can be added, edited, or removed from the **Customize** section.

Each product contains:
- Product name
- Price
- Category

### CSV Product Import
Products can also be imported in bulk using a CSV file.

Expected columns:

```csv
Product name,Price,Category
T-Shirt,2500,Clothing
Cap,1500,Accessories
Coffee,700,Drinks
```

The POS also includes a downloadable CSV template.

When importing, users can either:
- Add/update products while keeping existing products
- Replace the current product list entirely

### Sales Dashboard
The sales section shows:
- Revenue for the current day
- Number of orders
- Number of items sold
- Product sales breakdown
- Recent orders
- Order numbers
- Order completion status

Orders can be marked as **Completed** once they have been prepared or handed over to the customer.

Completed orders can also be reopened if they were marked accidentally.

### Sales Export
Daily sales can be exported as a CSV file.

The export includes information such as:
- Date
- Order number
- Order status
- Time
- Product
- Category
- Quantity
- Unit price
- Line total
- Order total
- Currency

### Payment Display
A dedicated **Payment** section can be shown to customers.

Users can configure:
- Payment QR code
- Bank name
- Account name
- Account number
- Branch
- Transfer instructions or payment notes

This makes it possible to turn the screen toward the customer so they can scan the QR code or copy the bank transfer details.

### Currency Settings
The POS supports several built-in currencies, including:
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

## How It Works

Simple POS is a static web application.

There is:
- No backend
- No database
- No login system
- No cloud sync
- No external POS service required

All application data is stored using the browser's `localStorage`.

This includes:
- Business / POS name
- Currency settings
- Products
- Categories
- Current cart
- Sales history
- Order completion status
- Payment QR code
- Bank transfer details

## Running the POS

### Option 1 — GitHub Pages

The easiest way to use Simple POS on a tablet or phone is to host it using GitHub Pages.

1. Add the HTML file to a GitHub repository.
2. Enable GitHub Pages for the repository.
3. Open the generated GitHub Pages URL in your browser.
4. On iPad or iPhone, open the page in Safari and use **Add to Home Screen** for an app-like experience.

### Option 2 — Desktop Browser

The HTML file can also be opened directly in a desktop browser for testing or local use.

For tablets and mobile devices, using a hosted version is recommended because some mobile operating systems do not execute locally opened HTML files normally.

## First-Time Setup

1. Open **Customize**.
2. Set the business or POS name.
3. Select the currency.
4. Add products manually or import them from CSV.
5. Add payment QR and bank details if required.
6. Return to **POS** and begin taking orders.

## Typical Order Workflow

1. Select a category or use **All Products**.
2. Tap products to add them to the current order.
3. Use the minus button if an item was added accidentally.
4. Confirm the total.
5. Place the order.
6. Call out the displayed order number when the order is ready.
7. Open **Sales** and mark the order as **Completed**.

## Data Storage and Backups

All data is stored locally on the device and browser being used.

This means:

- Refreshing or closing the page normally does **not** remove the data.
- Different devices have separate data.
- Different browser profiles have separate data.
- A different website/domain will have separate local storage.
- Clearing browser/site data can remove the POS data.

For important events or sales periods, it is recommended to export the daily sales CSV regularly.

Simple POS is intended for lightweight use and should not be treated as a replacement for a full accounting system or cloud-backed commercial POS.

## Privacy

Simple POS does not require an account and does not send POS data to a custom backend.

When hosted as a static site, order and configuration data remain in the browser's local storage.

The hosting provider will still handle normal web requests required to serve the page itself.

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

## Project Structure

The application is intentionally kept as a single HTML page containing:

- HTML
- CSS
- JavaScript

No build process is required.

## Contributing

Suggestions, improvements, bug reports, and contributions are welcome.

If you make changes that could be useful to other small vendors or pop-up operators, feel free to open an issue or pull request.

## License

This project is licensed under the GNU General Public License v3.0 (GPL-3.0).
You are free to use, study, modify, and redistribute the software under the terms of the GPL v3. If you distribute modified versions of the project, those versions must also be made available under the GPL v3 with their corresponding source code.

See the LICENSE file for the full license text.

## Initiative

Simple POS is made freely available as an open initiative under **Utpatti — The Creative Collective**.
