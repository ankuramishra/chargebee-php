# chargebee-php
Working chargebee library for php/Drupal environment.

require(DRUPAL_ROOT.'path to inti.php');
# generating invoice to existing customer on chargebee
use ChargeBee\ChargeBee\Environment;
use ChargeBee\ChargeBee\Models\Invoice;

Environment::configure("site_name","key");
$result = Invoice::createForChargeItemsAndCharges(array(
  "customerId" => "16BjkqSmSXMiFE0I",
  "shippingAddress" => array(
    "firstName" => "John",
    "lastName" => "Mathew",
    "city" => "Walnut",
    "state" => "California",
    "zip" => "91789",
    "country" => "US"
    ),
  "itemPrices" => array(array(
    "itemPriceId" => "Subscription-Plan-Group-USD",
    "unitPrice" => 200000))
  ));
$invoice = $result->invoice();
