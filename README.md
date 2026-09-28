# Simple POS

Simple POS is a free, lightweight point-of-sale system for pop-ups, small vendors, markets, and events. It runs entirely in the browser, requires no account or backend, and stores your products, orders, sales, branding, and payment details locally on your device.

Made freely available as an open initiative under **Utpatti — The Creative Collective**.

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
- Primary brand color
- Secondary / CTA color
- Page background color
- Card / surface color
- Main text color

For most users, it is recommended to change only the **Primary** and **Secondary / CTA** colors. The default background, surface, and text colors are designed to preserve readability and contrast.

#### Logo Recommendations

Horizontal or wordmark logos work best in the Simple POS header.

Recommended:

- Approximately a **4:1 aspect ratio**
- Example size: **800 × 200 px**
- Transparent PNG where possible

Square or tall logos are supported, but they will appear smaller in the header.

### Configuration Backup and Transfer

The complete POS setup can be exported as a JSON configuration file and imported on another device or browser.

The configuration file can include:

- Business / POS name
- Currency settings
- Brand colors
- Products
- Product accent colors
- Product menu notes
- Category order
- Payment information
- Optional brand logo
- Optional payment QR code

Sales history and the current cart are not included in configuration exports.

Users can choose whether to include the logo and payment QR when exporting. Images are embedded directly inside the JSON file, which makes the file larger but keeps the entire setup in a single file.

When importing a configuration:

- Current products and configuration are replaced
- Existing sales history is preserved
- The current cart is cleared
- If the imported file does not contain a logo or QR code, the logo and QR already stored on the device are preserved

CSV is intended for product import and editing, while JSON is intended for transferring or backing up the complete POS setup.

### Sales Dashboard

The Sales section shows:

- Revenue for the current day
- Number of orders
- Number of open orders
- Number of items sold
- Product sales breakdown
- Recent orders
- Order numbers
- Order completion status
- The next order number

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
- Using the POS on an iPad or phone
- Products and categories
- CSV product import
- Sales dashboard
- Payment display
- Configuration backup and transfer
- Data storage and backups
- Current limitations

## Customize Menu

The Customize section is split into four areas:

### General & Branding

Used for:

- Business / POS name
- Currency
- Brand logo
- Brand colors
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
- Brand logo
- Brand colors
- Products
- Product accent colors
- Product menu notes
- Category order
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
2. Under **General & Branding**, set the business / POS name and currency.
3. Optionally upload a logo and configure the primary and secondary brand colors.
4. Under **Products & Categories**, add products manually or import them from CSV.
5. Arrange categories in the order you want them displayed.
6. Optionally give individual products an accent color or short menu note.
7. Under **Payment Information**, add a payment QR code and bank details if required.
8. Return to **POS** and begin taking orders.

If you already have a Simple POS JSON configuration file, you can import it from **Customize → General & Branding → Configuration Backup & Transfer** to skip most of the manual setup.

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
- A different website or domain will have separate local storage.
- Clearing browser or site data can remove the POS data.

For important events or sales periods, it is recommended to export the daily sales CSV regularly.

Use the separate JSON configuration export to back up or transfer the POS setup itself.

### Sales CSV vs Configuration JSON

**Sales CSV**
- Contains daily sales information
- Useful for reporting, records, and external analysis

**Configuration JSON**
- Contains the POS setup
- Useful for moving a setup to another device or browser
- Can optionally include the brand logo and payment QR
- Does not contain sales history

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

This project is licensed under the **GNU General Public License v3.0 (GPL-3.0)**.

You are free to use, study, modify, and redistribute the software under the terms of the GPL v3. If you distribute modified versions of the project, those versions must also be made available under the GPL v3 with their corresponding source code.

See the [`LICENSE`](LICENSE) file for the full license text.

## Initiative

Simple POS is made freely available as an open initiative under **Utpatti — The Creative Collective**.
