# SEPA XML class

## About

SepaXML is a class that converts your direct debit information to PAIN.008.001.02 XML files. The original class is made by [BureauPartners](https://github.com/BureauPartners/SEPA-Incasso)

## Installation

The recommended installation way is through [Composer](https://getcomposer.org).

```bash
$ composer require wesselstam/sepa-xml
```

## Example

```php
use WesselStam\SepaXML;

// create instance
$oSEPA = new SepaXML();

// Set your collection destination information
$oSEPA->setCollectionDestination(
    "Your company name, 
    "Your IBAN", 
    "Your BIC", 
    "Your Creditor ID"
);

// Set the direct debit date
$oSEPA->setDate("2017-07-11");

// Add one or more collections to the 
// addCollection($sName, $sIBAN, $sBIC, $iAmount, $sDescription, $sSignedDate, $sMandateID)
$oSEPA->addCollection(
    "Customer name",
    "Customer IBAN",
    "Customer BIC",
    "Amount",
    "Description",
    "Mandate date",
    "Mandate ID"
);


// output
echo $oSEPA->getXML();
```

## Source
https://github.com/BureauPartners/SEPA-Incasso