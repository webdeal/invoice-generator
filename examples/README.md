# Kenod Invoice Generator Examples

This directory contains examples demonstrating the modern `Kenod\InvoiceGenerator` library.

## Example Overview

### 01_basic_invoice.php
Simple basic invoice example:
- Minimal configuration
- Supplier and customer
- Payment details
- Several items with VAT
- Perfect starting point for your projects

**Run:**
```bash
php 01_basic_invoice.php
```

### 02_eet.php
Invoice with Electronic Registration of Sales (EET):
- EET system integration
- FIK, PKP, BKP codes
- Standard/simplified mode
- Grey color scheme

**Run:**
```bash
php 02_eet.php
```

### 03_reverse_charge.php
Invoice with reverse charge VAT:
- Suitable for EU transactions
- No VAT calculation
- "Tax to be paid by customer" text

**Run:**
```bash
php 03_reverse_charge.php
```

### 04_translations.php
Translation example with Slovak language:
- Slovak language (sk)
- EUR currency
- Translated texts and labels

**Run:**
```bash
php 04_translations.php
```

### 05_eco_print.php
Eco-friendly print - minimal ink consumption:
- White background
- Black borders
- Unit column display
- Extended supplier details (web, email, phone)
- Notes below items

**Run:**
```bash
php 05_eco_print.php
```

### 06_images.php
Adding images to invoice:
- Logo on all pages ('A')
- Watermark on last page ('L')
- Additional logo on first page ('F')
- Various image positions

**Run:**
```bash
php 06_images.php
```

### 07_custom_callback.php
Using custom callback function:
- Adding custom text
- Access to all TCPDF methods
- Watermarks, shapes, additional content

**Run:**
```bash
php 07_custom_callback.php
```

### 08_english.php
English language invoice example:
- English localization (en)
- International invoice
- All texts translated to English

**Run:**
```bash
php 08_english.php
```

### 09_multiple_documents.php
Generating multiple documents in one PDF:
- Complete invoice with EET data
- Second invoice with different data
- Delivery note (non-VAT document)
- Using `clearData()` method between documents
- Advanced settings and styling

**Run:**
```bash
php 09_multiple_documents.php
```

### 10_credit_note.php
Credit note (corrective tax document):
- Document type: credit note/correction (`setDocumentType(3)`)
- Reference to original invoice (`setAdditionalInfo()`)
- Negative amounts for refunds
- Barcode with document number (`setBarcode()`)
- Custom VAT rate labels (`setVatRates()`)
- Item spacing (`setItemSpacing()`)
- Signature texts (`setSignatureText()`)
- Footer texts (`setFooterText()`)
- Constant and specific symbols
- Blue color scheme with borders

**Run:**
```bash
php 10_credit_note.php
```

### 11_comprehensive.php
Comprehensive test with all available features:
- **All settings methods**: document configuration, styling, borders, underlines
- **All address fields**: supplier, customer, end recipient with all properties
- **All information fields**: dates, order numbers, custom parameters
- **All payment details**: payment method, account, symbols, custom fields
- **Multiple items**: different VAT rates, quantities, units, notes
- **Advanced features**: QR payment, barcode, EET, discount, rounding, deposits
- **Images and branding**: logo placement, styling
- **Custom callback**: TCPDF extension
- Perfect for testing and as a complete reference

**Run:**
```bash
php 11_comprehensive.php
```

## Legacy Examples (Old API)

For reference, older examples using the original API are also available:
- `generuj_fakturu.php` - Complex example with old version
- `eet.php` - EET with original API
- `reverse_charge.php` - Reverse charge with original API
- `preklady.php` - Translations with original API
- `ekonomicky_tisk.php` - Eco print with original API
- `obrazky.php` - Images with original API
- `custom_callback.php` - Custom callback with original API
- `vice_dokladu.php` - Multiple documents in one PDF

**Note:** These files use the older `\WFPfaktury\WFPfaktury` namespace and are not compatible with the new version.

## Migration from Old Version

To migrate from the old version to the new one, see the [MIGRATION.md](../MIGRATION.md) file in the root directory.

Main changes:
- Namespace: `\WFPfaktury\WFPfaktury` → `Kenod\InvoiceGenerator\InvoiceGenerator`
- Method names: `SetJmeno()` → `setName()`, `SetCisloFaktury()` → `setInvoiceNumber()`, etc.
- Fluent interface: all setters return `$this` for chaining
- Typed properties: PHP 8.3+ strict types
- Property access: `$invoice->supplier` → `$invoice->getSupplier()`

## Running All Examples

To test all new examples at once:

```bash
# Run individual examples
php 01_basic_invoice.php
php 02_eet.php
# ... etc

# Or create a test script to run them all
for file in 01_*.php 02_*.php 03_*.php 04_*.php 05_*.php 06_*.php 07_*.php 08_*.php 09_*.php 10_*.php 11_*.php; do
    echo "Testing $file..."
    php "$file"
done
```

## API Documentation

Complete documentation of all classes and methods is available in the root directory:
- [README.md](../README.md) - Basic overview and installation
- [MIGRATION.md](../MIGRATION.md) - Migration guide
- PhpDoc comments in source files

## Support

For questions and bug reports, use GitHub Issues:
https://github.com/kenod/invoice-generator/issues

## Links

- **Official Website**: https://faktury.chci-www.cz/
- **Interactive Demo**: https://fakturasnadno.cz/ - Try different invoice options online
