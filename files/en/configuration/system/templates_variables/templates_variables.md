Variables for templates
=======================

There is the list of all variables which are using in templates. So you can use them in your custom templates.

####Basic system values:
<details>
<summary>{{ dump(loader.values) }}</summary>
<p markdown="1">

##### result will be array of company fields:

     object(models\common\finance\TemplateValues)#226 (30) {
     ["id"]=> string(2) "13"
     ["invoice_template_id"]=> string(1) "5"
     ["request_template_id"]=> string(2) "14"
     ["receipt_template_id"]=> string(2) "34"
     ["reminder_mail_template_id"]=> string(2) "15"
     ["reminder_sms_template_id"]=> string(2) "16"
     ["company_name"]=> string(33) "Private Company Internet Ltd."
     ["street_1"]=> string(47) "56, Adamause str."
     ["street_2"]=> string(0) ""
     ["zip"]=> string(6) "568749"
     ["city"]=> string(8) "Yamayka"
     ["country"]=> string(5) "Gonduras"
     ["email"]=> string(20) "office@privatecompany.com"
     ["phone"]=> string(14) "8 500 600 8526"
     ["company_id"]=> string(21) "K683621TP2398723321"
     ["company_vat"]=> string(0) ""
     ["vat_percent"]=> string(7) "20.0000"
     ["bank_account"]=> string(0) ""
     ["bank_name"]=> string(0) ""
     ["bank_id"]=> string(0) ""
     ["bank_address"]=> string(0) ""
     ["splynx_url"]=> string(44) "https://privatecompany/admin/login"
     ["partner_percent"]=> string(4) "0.00"
     ["deleted"]=> NULL
     ["_relations":"db\Record":private]=> array(0) { }
     ["connected_models":"db\Record":private]=> NULL
     ["_oldAttributes":protected]=> array(23) {
             some old attributes ...
             }
     ["_errors":"base\Model":private]=> NULL
     ["_additionalAttributes":protected]=> array(0) { }
     ["_isAdditionalAttributesLoaded":protected]=> bool(false)
     }
</p>
</details>

####Customer's information:
<details>
<summary>{{ dump(customer) }}</summary>
<p markdown="1">

##### result will be array of customer fields:

     array(38) {
     ["id"]=> string(1) "4"
     ["billing_type"]=> string(7) "prepaid"
     ["partner_id"]=> string(2) "13"
     ["location_id"]=> string(1) "3"
     ["added_by"]=> string(5) "admin"
     ["added_by_id"]=> string(1) "1"
     ["login"]=> string(11) "qwerty"
     ["category"]=> string(6) "person"
     ["password"]=> string(11) "ZaXsCdVfBg"
     ["name"]=> string(12) "Qwert Ytrewq"
     ["email"]=> string(19) "qwerty@gmail.com"
     ["phone"]=> string(10) "132456789"
     ["street_1"]=> string(57) "Long Island str., 526/4"
     ["zip_code"]=> string(0) "48567"
     ["city"]=> string(0) "Malibu"
     ["status"]=> string(6) "active"
     ["date_add"]=> string(10) "2016-05-21"
     ["last_online"]=> string(19) "2017-06-01 11:41:01"
     ["last_update"]=> string(19) "2017-05-01 14:10:50"
     ["internet_tariffs"]=> NULL
     ["voice_tariffs"]=> NULL
     ["custom_tariffs"]=> NULL
     ["services_internet_router_id"]=> NULL
     ["services_internet_sector_id"]=> NULL
     ["services_internet_login"]=> NULL
     ["services_internet_ipv4"]=> NULL
     ["services_internet_ipv4_route"]=> NULL
     ["services_internet_mac"]=> NULL
     ["services_voice_phone"]=> NULL
     ["services_voice_voice_device_id"]=> NULL
     ["services_internet_start_date"]=> NULL
     ["services_internet_end_date"]=> NULL
     ["services_voice_start_date"]=> NULL
     ["services_voice_end_date"]=> NULL
     ["services_custom_start_date"]=> NULL
     ["services_custom_end_date"]=> NULL
     ["deleted"]=> string(1) "0"
     ["additional_attributes"]=> array(10) {
             ["some_additional_field"]=> string(0) "some additional field"
             }
     }
</p>
</details>

####General information:
<details>
<summary>{{ dump(loader.info) }}</summary>
<p markdown="1">

##### result will be array of customer's information fields:

     object(models\common\customers\CustomerInfo)#226 (12) {
     ["customer_id"]=> string(1) "4"
     ["birthday"]=> string(0) ""
     ["passport"]=> string(0) ""
     ["company_id"]=> string(0) ""
     ["vat_id"]=> string(0) ""
     ["deleted"]=> NULL
     ["_relations":"db\Record":private]=> array(0) { }
     ["connected_models":"db\Record":private]=> NULL
     ["_oldAttributes":protected]=> array(5) {
             some old attributes ...
             }
     ["_errors":"base\Model":private]=> NULL
     ["_additionalAttributes":protected]=> array(0) { }
     ["_isAdditionalAttributesLoaded":protected]=> bool(false)
     }
</p>
</details>

####Get all Internet services that are Active:
<details>
<summary>{{ dump(loader.getServicesByTypeAndStatus('internet', 'active')) }}</summary>
<p markdown="1">

##### result will be array of service fields:

     array(1) {
     [0]=> object(models\common\customers\ServicesInternet)#235 (47) {
     ["type"]=> string(8) "internet"
     ["router_id"]=> string(1) "0"
     ["login"]=> string(11) "qwerty_login"
     ["password"]=> string(11) "qwert_pass"
     ["sector_id"]=> string(1) "0"
     ["taking_ipv4"]=> string(1) "0"
     ["ipv4"]=> string(0) ""
     ["ipv4_pool_id"]=> string(1) "0"
     ["taking_ipv6"]=> string(1) "0"
     ["ipv6"]=> string(0) ""
     ["ipv6_pool_id"]=> string(1) "0"
     ["mac"]=> string(0) ""
     ["port_id"]=> string(1) "0"
     ["ipv4_route"]=> string(0) ""
     ["ipv6_route"]=> string(0) ""
     ["update_online_tariff":"models\common\customers\ServicesInternet":private]=> bool(false)
     ["_is_password_changed":"models\common\customers\ServicesInternet":private]=> bool(false)
     ["parent_id"]=> string(1) "0"
     ["customer_id"]=> string(1) "4"
     ["tariff_id"]=> string(3) "206"
     ["description"]=> string(9) "Internet tariff - 30Mb"
     ["quantity"]=> string(1) "1"
     ["unit"]=> string(0) ""
     ["unit_price"]=> string(9) "100"
     ["start_date"]=> string(10) "2017-01-16"
     ["end_date"]=> string(10) "0000-00-00"
     ["discount"]=> string(1) "0"
     ["discount_percent"]=> string(4) "0.00"
     ["discount_start_date"]=> string(10) "0000-00-00"
     ["discount_end_date"]=> string(10) "0000-00-00"
     ["discount_text"]=> string(0) ""
     ["status"]=> string(6) "active"
     ["status_new"]=> string(0) ""
     ["old_tariff_id"]=> NULL
     ["planned_date"]=> NULL
     ["validate_login"]=> bool(true)
     ["skip_some_validations"]=> bool(false)
     ["id"]=> string(4) "83"
     ["ips_to_remove":"db\ActiveTable":private]=> array(0) { } ["relatedItems":protected]=> array(0) { }
     ["deleted"]=> string(1) "0"
     ["_relations":"db\Record":private]=> array(0) { }
     ["connected_models":"db\Record":private]=> NULL
     ["_oldAttributes":protected]=> array(32) {
             some old attributes ...
             }
     }
</p>
</details>

####Bundles:
<details>
<summary>{% set bundles = loader.getBundles() %} {{ dump(bundles) }}</summary>
<p markdown="1">

##### result will be array of all Bundles fields:


     array(2) {
      [1]=> object(models\admin\tariffs\Bundle)#117 (34) {
         ["id"]=> string(1) "1"
         ["title"]=>  string(3) "New"
         ["service_description"]=>  string(4) "New1"
         ["price"]=> string(7) "10.0000"
         ["customers"]=> NULL
         ["services"]=> NULL
          ["with_vat"]=> string(1) "1"
          ["vat_percent"]=> string(6) "0.0000"
          ["partner_ids"]=> array(3) {
              [0]=> string(1) "1"
             [1]=> string(1) "2"
              [2]=> string(1) "3"
          }
          ["activation_fee"]=> string(6) "0.0000"
          ["get_activation_fee_when"]=> string(21) "first_service_billing"
          ["issue_invoice_while_service_creation"]=> string(1) "0"
          ["contract_duration"]=> string(1) "0"
          ["automatic_renewal"]=> string(1) "0"
          ["auto_reactivate"]=> string(1) "0"
          ["prior_cancellation_fee"]=> string(6) "0.0000"
          ["change_to_other_bundle_fee"]=> string(6) "0.0000"
          ["discount_period"]=> string(1) "0"
          ["discount_percent"]=> string(6) "0.0000"
          ["internet_tariffs"]=> array(1) {
              [0]=> string(1) "2"
         }
         ["voice_tariffs"]=> array(0) {
         }
         ["custom_tariffs"]=> array(0) {
         }
         ["_recalculateBlockingDate":"models\admin\tariffs\Bundle":private]=> bool(false)
         ["_ips_to_remove":"db\ActiveTable":private]=> array(0) {
         }
         ["_disableRequiredRuleForAdditionalAttribute":"db\ActiveTable":private]=> bool(false)
         ["deleted"]=> string(1) "0"
         ["_changedAttributes":"db\Record":private]=> NULL
         ["_relations":"db\Record":private]=> array(0) {
         }
         ["_connected_models":"db\Record":private]=> NULL
         ["relatedItems":protected]=> array(0) {
         }
     ...
         }
      [2]=> object(models\admin\tariffs\Bundle)#119 (34) {
      ["id"]=> string(1) "2"
      ["title"]=> string(20) "Bundle with discount"
      ["service_description"]=> string(20) "Bundle with discount"
      ["price"]=> string(8) "100.0000"
      ["customers"]=> NULL
      ["services"]=> NULL
      ["with_vat"]=> string(1) "1"
      ["vat_percent"]=> string(6) "0.0000"
      ["partner_ids"]=> array(2) {
         [0]=> string(1) "1"
      [  1]=> string(1) "2"
      }
      ["activation_fee"]=> string(6) "0.0000"
      ["get_activation_fee_when"]=> string(21) "first_service_billing"
      ["issue_invoice_while_service_creation"]=> string(1) "0"
      ["contract_duration"]=> string(2) "12"
      ["automatic_renewal"]=> string(1) "1"
      ["auto_reactivate"]=>  string(1) "0"
      ["prior_cancellation_fee"]=> string(6) "0.0000"
      ["change_to_other_bundle_fee"]=> string(6) "0.0000"
      ["discount_period"]=> string(2) "12"
      ["discount_percent"]=> string(7) "20.0000"
      ["internet_tariffs"]=> array(1) {
         [0]=> string(1) "9"
      }
      ["voice_tariffs"]=> array(0) {
      }
      ["custom_tariffs"]=> array(0) {
      }
      ...
     }
</p>
</details>

####Services from Bundles:
<details>
<summary>{% set servisesBundle = loader.getServicesBundle() %} {{ dump(servisesBundle) }}</summary>
<p markdown="1">

##### result will be array of the Bundle and all Services fields:

     array(1) {
      [4]=> object(models\common\customers\services\ServicesBundle)#407 (35) {
      ["parent_id"]=> string(1) "0"
      ["customer_id"]=> string(4) "5001"
      ["bundle_id"]=> string(1) "1"
      ["description"]=> string(4) "New1"
      ["unit_price"]=> string(7) "10.0000"
      ["start_date"]=> string(10) "2018-10-22"
      ["end_date"]=> string(10) "2019-01-21"
      ["automatic_renewal"]=> string(1) "0"
      ["activation_fee_transaction_id"]=> string(1) "0"
      ["prior_cancellation_fee_transaction_id"]=> string(1) "0"
      ["discount"]=> string(1) "0"
      ["discount_percent"]=> string(4) "0.00"
      ["discount_start_date"]=> string(10) "2018-10-22"
      ["discount_end_date"]=> string(10) "0000-00-00"
      ["discount_text"]=> string(0) ""
      ["status"]=> string(6) "active"
      ["period"]=> string(2) "-1"
      ["type"]=> string(6) "bundle"
      ["services_internet"]=> array(1) {
         [130]=> object(models\common\customers\ServicesInternet)#415 (51) {
         ["type"]=> string(8) "internet"
         ["router_id"]=> string(1) "0"
         ["login"]=> string(11) "00500123456"
         ["password"]=> string(0) ""
         ["sector_id"]=> string(1) "0"
         ["taking_ipv4"]=> string(1) "0"
         ["ipv4"]=> string(0) ""
         ["ipv4_pool_id"]=> string(1) "0"
         ["taking_ipv6"]=> string(1) "0"
         ["ipv6"]=> string(0) ""
         ["ipv6_pool_id"]=> string(1) "0"
         ["mac"]=> string(0) ""
         ["port_id"]=> string(0) ""
         ["ipv4_route"]=> string(0) ""
         ["ipv6_route"]=> string(0) ""
      }
     ....
     }
</p>
</details>

####Billing information:
<details>
<summary>{{ dump(loader.billing) }}</summary>
<p markdown="1">

##### result will be array of billing fields:

     object(models\common\customers\CustomerBilling)#226 (36) {
     ["customer_id"]=> string(1) "4"
     ["enabled"]=> string(1) "1"
     ["type"]=> string(1) "1"
     ["deposit"]=> string(8) "758.0000"
     ["billing_date"]=> string(1) "1"
     ["billing_due"]=> string(2) "15"
     ["grace_period"]=> string(2) "10"
     ["make_invoices"]=> string(1) "1"
     ["auto_pay_invoices_from_deposit"]=> string(0) ""
     ["payment_method"]=> string(1) "1"
     ["min_balance"]=> string(6) "0.0000"
     ["request_auto_enable"]=> string(0) ""
     ["request_auto_day"]=> string(1) "1"
     ["request_auto_period"]=> string(1) "0"
     ["reminder_enable"]=> string(1) "1"
     ["reminder_day_1"]=> string(1) "2"
     ["reminder_day_2"]=> string(1) "8"
     ["reminder_day_3"]=> string(2) "20"
     ["reminder_payment"]=> string(0) ""
     ["reminder_payment_value"]=> string(6) "0.0000"
     ["reminder_payment_comment"]=> string(0) ""
     ["reminder_type"]=> string(1) "0"
     ["billing_person"]=> string(0) ""
     ["billing_street_1"]=> string(0) ""
     ["billing_zip_code"]=> string(0) ""
     ["billing_city"]=> string(0) ""
     ["request_auto_type"]=> string(1) "1"
     ["request_auto_next"]=> string(10) "0000-00-00"
     ["partner_id"]=> NULL ["deleted"]=> string(1) "0"
     ["_relations":"db\Record":private]=> array(0) { }
     ["connected_models":"db\Record":private]=> NULL
     ["_oldAttributes":protected]=> array(29) {
             some old attributes ...
             }
     ["_errors":"base\Model":private]=> NULL
     ["_additionalAttributes":protected]=> array(0) { }
     ["_isAdditionalAttributesLoaded":protected]=> bool(false)
     }
</p>
</details>

####Partner:
<details>
<summary>{{ dump(loader.partner) }}</summary>
<p markdown="1">

##### result will be array of partner fields:

     object(models\admin\administration\Partners)#226 (11) {
     ["id"]=> string(2) "13"
     ["name"]=> string(14) "Partner West"
     ["ips_to_remove":"db\ActiveTable":private]=> array(0) { }
     ["relatedItems":protected]=> array(0) { }
     ["deleted"]=> string(1) "0"
     ["_relations":"db\Record":private]=> array(0) { }
     ["connected_models":"db\Record":private]=> NULL
     ["_oldAttributes":protected]=> array(3) {
             ["id"]=> string(2) "13"
             ["name"]=> string(14) "Partner West"
             ["deleted"]=> string(1) "0"
             }
     ["_errors":"base\Model":private]=> NULL
     ["_additionalAttributes":protected]=> array(1) {
             ["code"]=> string(4) "EUR"
             }
     ["_isAdditionalAttributesLoaded":protected]=> bool(true) }
</p>
</details>

####Transactions:
<details>
<summary>{{ dump(loader.transactions) }}</summary>
<p markdown="1">

##### result will be array of transactions fields:

     array(3) {
     [158]=> object(models\common\finance\Transactions)#226 (32) {
             ["id"]=> string(4) "158"
             ["customer_id"]=> string(1) "4"
             ["type"]=> string(6) "credit"
             ["quantity"]=> string(1) "1"
             ["unit"]=> string(0) ""
             ["price"]=> string(9) "1033.8500"
             ["tax_percent"]=> string(6) "0.0000"
             ["total"]=> string(9) "1033.8500"
             ["date"]=> string(10) "2017-05-11"
             ["category"]=> string(1) "3"
             ["description"]=> string(11) "Credit Card"
             ["period_from"]=> string(10) "0000-00-00"
             ["period_to"]=> string(10) "0000-00-00"
             ["service_id"]=> string(1) "0"
             ["payment_id"]=> string(3) "366"
             ["invoice_id"]=> string(1) "0"
             ["invoiced_by_id"]=> string(1) "0"
             ["comment"]=> string(15) "Pay by Credit Card"
             ["to_invoice"]=> string(1) "0"
             ["service_type"]=> string(8) "internet"
             ["source"]=> string(6) "manual"
             ["balance"]=> NULL
             ["total_with_tax"]=> NULL
             ["ips_to_remove":"db\ActiveTable":private]=> array(0) { }
             ["relatedItems":protected]=> array(0) { }
             ["deleted"]=> string(1) "0"
             ["_relations":"db\Record":private]=> array(0) { }
             ["connected_models":"db\Record":private]=> NULL
             ["_oldAttributes":protected]=> array(22) { [
                     some old attributes ...
                     }
             ["_errors":"base\Model":private]=> NULL     
             ["_additionalAttributes":protected]=> array(0) { }
             ["_isAdditionalAttributesLoaded":protected]=> bool(false)
             }
     [681]=> object(models\common\finance\Transactions)#224 (32) {
             The same attributes
             }
     [985]=> object(models\common\finance\Transactions)#223 (32) {
             The same attributes
             }
</p>
</details>

####Invoices variables:
<details>
<summary>{{ dump(loader.invoices) }}</summary>
<p markdown="1">

##### result will be array of invoices variables fields:

     array(1) { [685]=> object(models\common\finance\Invoices)#226 (29) {
     ["id"]=> string(4) "685"
     ["customer_id"]=> string(1) "4"
     ["date_created"]=> string(10) "2017-05-31"
     ["real_create_datetime"]=> string(19) "2017-06-01 00:00:13"
     ["date_updated"]=> string(10) "2017-06-01"
     ["date_payment"]=> string(10) "2017-05-31"
     ["date_till"]=> string(10) "2017-06-15"
     ["use_transactions"]=> string(1) "1"
     ["note"]=> string(0) ""
     ["memo"]=> string(0) ""
     ["number"]=> string(12) "201713000183"
     ["total"]=> string(8) "533.6000"
     ["payment_id"]=> string(1) "0"
     ["payd_from_deposit"]=> string(1) "1"
     ["status"]=> string(4) "paid"
     ["mark"]=> NULL
     ["recalculated"]=> bool(false)
     ["noCache"]=> bool(false)
     ["is_sent"]=> string(1) "0"
     ["disable_cache"]=> NULL
     ["ips_to_remove":"db\ActiveTable":private]=> array(0) { }
     ["relatedItems":protected]=> array(0) { }
     ["deleted"]=> string(1) "0"
     ["_relations":"db\Record":private]=> array(0) { }
     ["connected_models":"db\Record":private]=> NULL
     ["_oldAttributes":protected]=> array(17) {
             some old attributes ...
             }
     }
</p>
</details>

####Invoice items:
<details>
<summary>{% for invoice in loader.getInvoices() %} ...</summary>
<p markdown="1">

##### {% for invoice in loader.getInvoices() %}
     Invoice {{ invoice.number}} items:
     {{ dump(invoice.items) }}
     {% endfor %}
     {{ dump(loader.invoices) }}



     result will be array of tariff field and invoices fields:

     Invoice 201713000183 items:
     array(1) {
     [0]=> array(12) {
             ["id"]=> string(4) "948"
             ["invoice_id"]=> string(4) "684"
             ["pos"]=> string(1) "0"
             ["description"]=> string(9) "Internet tariff - 30Mb"
             ["quantity"]=> string(1) "1"
             ["unit"]=> string(0) ""
             ["price"]=> string(8) "464.0000"    
             ["tax"]=> string(7) "15.0000"
             ["period_from"]=> string(10) "2017-05-14"
             ["period_to"]=> string(10) "2017-05-31"
             ["transaction_id"]=> string(4) "984"
             ["deleted"]=> string(1) "0"
             }
     }
     array(1) {
     [948]=> object(models\common\finance\Invoices)#280 (29) {
             ["id"]=> string(4) "948"
             ["customer_id"]=> string(1) "4"
             ["date_created"]=> string(10) "2017-05-31"
             ["real_create_datetime"]=> string(19) "2017-06-01 00:00:13"
             ["date_updated"]=> string(10) "2017-06-01"
             ["date_payment"]=> string(10) "2017-05-31"
             ["date_till"]=> string(10) "2017-06-15"
             ["use_transactions"]=> string(1) "1"
             ["note"]=> string(0) ""
             ["memo"]=> string(0) ""
             ["number"]=> string(12) "201713000183"
             ["total"]=> string(8) "533.6000"
             ["payment_id"]=> string(1) "0"
             ["payd_from_deposit"]=> string(1) "1"
             ["status"]=> string(4) "paid"
             ["mark"]=> NULL
             ["recalculated"]=> bool(false)
             ["noCache"]=> bool(false)
             ["is_sent"]=> string(1) "0"
             ["disable_cache"]=> NULL
             ["ips_to_remove":"db\ActiveTable":private]=> array(0) { }
             ["relatedItems":protected]=> array(0) { }
             ["deleted"]=> string(1) "0"
             ["_relations":"db\Record":private]=> array(0) { }
             ["connected_models":"db\Record":private]=> NULL
             ["_oldAttributes":protected]=> array(17) {
                     some old attributes ...
                     }
             }
     }
</p>
</details>

####Pro-formas:
<details>
<summary>{{ dump(loader.requests) }}</summary>
<p markdown="1">

##### result will be array of pro-forma fields:

     array(1) {
     [2]=> object(models\common\finance\Requests)#226 (23) {
             ["id"]=> string(1) "2"
             ["customer_id"]=> string(1) "4"
             ["date_created"]=> string(10) "2017-06-07"
             ["real_create_datetime"]=> string(19) "2017-06-07 14:56:25"
             ["date_updated"]=> string(10) "2017-06-07"
             ["date_payment"]=> string(10) "0000-00-00"
             ["date_till"]=> string(10) "2017-06-22"
             ["number"]=> string(10) "2017000002"
             ["total"]=> string(8) "180.0000"    
             ["payment_id"]=> string(1) "0"
             ["status"]=> string(8) "not_paid"
             ["is_sent"]=> string(1) "0"
             ["note"]=> string(4) "Note"
             ["memo"]=> string(4) "Memo"
             ["ips_to_remove":"db\ActiveTable":private]=> array(0) { }
             ["relatedItems":protected]=> array(0) { }
             ["deleted"]=> string(1) "0"
             ["_relations":"db\Record":private]=> array(0) { }   
             ["connected_models":"db\Record":private]=> NULL
             ["_oldAttributes":protected]=> array(15) {
                     some old attributes ...
                     }
             ["_errors":"base\Model":private]=> NULL
             ["_additionalAttributes":protected]=> array(0) { }
             ["_isAdditionalAttributesLoaded":protected]=> bool(false)
             }
     }
</p>
</details>

####Payments:
<details>
<summary>{{ dump(loader.payments) }}</summary>
<p markdown="1">

##### result will be array of payment fields:

     array(1) {
     [366]=> object(models\common\finance\Payments)#226 (28) {
             ["id"]=> string(3) "366"
             ["customer_id"]=> string(1) "4"
             ["invoice_id"]=> string(1) "0"
             ["request_id"]=> string(1) "0"
             ["transaction_id"]=> string(4) "2400"
             ["payment_type"]=> string(2) "10"
             ["receipt_number"]=> string(13) "2017-10-00011"
             ["date"]=> string(10) "2017-05-13"
             ["real_create_datetime"]=> string(19) "2017-05-13 09:19:02"
             ["amount"]=> string(9) "1033.8500"
             ["comment"]=> string(15) "Pay by Bank Transfer"
             ["is_sent"]=> string(1) "1"
             ["field_1"]=> string(0) ""
             ["field_2"]=> string(10) "UNIC00032"
             ["field_3"]=> string(10) "UNIC00032"
             ["field_4"]=> string(13) "Payment: null"
             ["field_5"]=> string(19) "Bank Statement: 23"
             ["note"]=> string(0) ""
             ["memo"]=> string(0) ""
             ["ips_to_remove":"db\ActiveTable":private]=> array(0) { }
             ["relatedItems":protected]=> array(0) { }
             ["deleted"]=> string(1) "0"
             ["_relations":"db\Record":private]=> array(0) { }
             ["connected_models":"db\Record":private]=> NULL
             ["_oldAttributes":protected]=> array(20) {
                     some old attributes ...
                     }
             ["_errors":"base\Model":private]=> NULL
             ["_additionalAttributes":protected]=> array(0) { }
             ["_isAdditionalAttributesLoaded":protected]=> bool(false)
             }
     }
</p>
</details>

####Attached documents:
<details>
<summary>Invoices: {{ dump(loader.getAttac ...</summary>
<p markdown="1">

##### Invoices:
     {{ dump(loader.getAttachedInvoices) }}
     Pro-formas:
     {{ dump(loader.getAttachedRequests) }}
     Payment receipts:
     {{ dump(loader.getAttachedReceipts) }}




     result will be array of attached documents fields:

     array(1) {

     }
</p>
</details>


####Ignore Notification
<details>
<summary>Ignore Notification</summary>
<p markdown="1">

##### Example:
     {% if customer.billing_type == 'prepaid' %}
     === IGNORE NOTIFICATION ===
     {% else %}
     example  {{ customer.login }}
     {% endif %}



if the template result is "=== IGNORE NOTIFICATION ===" the notification will not be sent

</p>
</details>



And now, you can see **examples** how to use variables in templates:
```
Hello!

This is example template. We use Twig as template engine!
You can use some variables in templates.
For example to get customer name use {{ customer.name }},
customer login - {{ customer.login }}.
```

```
{% set billing_custom = loader.billing %}

Hello {{ customer.name}},
your deposit is {{ billing_custom.deposit }} EUR,
we strongly recommended to refill it.
```

```

{{ App.t('common', 'Hello') }} {{ customer.name }},
We would like to welcome you as a Super ISP!
Your Billing date will be {{ loader.billing.billing_date }} of every month.
There is no fixed length contract and you will be billed 1 month in advance.
Your customer reference number is {{ loader.customer.id }}
The e-mail address to where your invoices will be sent is : {{ loader.customer.email }}
Your Wifi password is: {{ loader.customer.additionalAttributes.wifi_pass }}


To download your invoices, view payments, create support tickets, see your usage statistics, use our customer self service portal my.splynx.com using username {{ loader.customer.login }} and {{ loader.customer.password }} as your password.

Our phone numbers in case you have not saved them yet,

1234567890
1234567890

office@superisp.com
```



####Here you can find example of Document - Contract:
<details>
<summary>Template of a Contract</summary>
<div markdown="1">

```bash     
     <!DOCTYPE html>
     <html lang="en">
     <head>
     <meta charset="UTF-8">
     <title></title>
     <style>
     td, th, tr {
     border: 1px solid black;
     word-wrap: break-word;
     }

     table {
     border-collapse: collapse;
     table-layout: fixed;
     font-family: Arial, Verdana, sans-serif;
     font-size: 10px;
     }

     .fs {
     font-family: Arial, Verdana, sans-serif;
     font-size: 10px;
     }

     body {
     margin: 10px;
     padding: 10px;
     }
     </style>
     </head>
     <body>
     <div style="text-align: center" class="fs"><h4>SUBSCRIBER CONTRACT AGREEMENT No. {{ customer.id }} </h4>
     entered into between
     </div>
     <br>
     <div>
     <table style="width:100%">
     <tr>
     <td bgcolor="#e0e0e0" style="width: 15%"><b>Company Name:</b></td>
     <td colspan="3">BEST ISP</td>
     </tr>
     <tr>
     <td bgcolor="#e0e0e0"><b>VAT id:</b></td>
     <td colspan="3">123455667</td>
     </tr>
     <tr>
     <td bgcolor="#e0e0e0"><b>Address</b></td>
     <td colspan="3">5 Main Street, Gotham city, 12345</td>
     </tr>
     <tr>
     <td bgcolor="#e0e0e0"><b>Phone number:</b></td>
     <td colspan="3">123456788</td>
     </tr>
     <tr>
     <td bgcolor="#e0e0e0"><b>Email</b></td>
     <td colspan="3">office@bestisp.com</td>
     </tr>
     <tr>
     <td bgcolor="#e0e0e0"><b>Date</b></td>
     <td style="width: 30%">{{ "now"|date("m/d/Y") }}</td>
     <td bgcolor="#e0e0e0" style="width: 10%"><b>Place</b></td>
     <td>Gotham city</td>
     </tr>
     <tr>
     <td bgcolor="#e0e0e0"><b>Signature</b><br>Employee of BEST ISP</td>
     <td colspan="3"></td>
     </tr>
     </table>
     </div>
     <br>
     <div style="text-align: center">(<b>"SERVICE PROVIDER"</b>) and
     </div>
     <br>
     <div>
     <table style="width:100%">
     <tr>
     <td bgcolor="#e0e0e0" style="width: 15%"><b>Name and Surname /<br>Company name</b></td>
     <td colspan="3">{{ customer.name }}</td>
     </tr>
     <tr>
     <td bgcolor="#e0e0e0"><b>Connection Address</b></td>
     <td colspan="3"> {{ loader.customer.street_1 }}{% if loader.customer.additionalAttributes.street_2 is not empty %}, {{ loader.customer.additionalAttributes.street_2 }}{% endif %}, {{ customer.city}}{% if loader.customer.zip_code is not empty %}, {{ loader.customer.zip_code }}{% endif %}</td>
     </tr>

     <tr>
     <td bgcolor="#e0e0e0"><b>Email</b><br>Invoices and receipts will be sent to this address</td>
     <td colspan="3">{{ loader.customer.email }}</td>
     </tr>
     <tr>
     <td bgcolor="#e0e0e0"><b>Phone</b></td>
     <td colspan="3">{{ loader.customer.phone }}</td>
     </tr>
     {% if loader.customer.additionalAttributes.contact_2 is not empty %}
     <tr>
     <td bgcolor="#e0e0e0"><b>Authorized person:</b></td>
     <td colspan="3">{{ loader.customer.additionalAttributes.contact_2 }}</td>
     </tr>
     {% endif %}
     {% if loader.customer.additionalAttributes.phone_2 is not empty %}
     <tr>
     <td bgcolor="#e0e0e0"><b>Authorized person's phone</b></td>
     <td colspan="3">{{ loader.customer.additionalAttributes.phone_2 }}</td>
     </tr>
     {% endif %}
     {% if loader.customer.additionalAttributes.contact_3 is not empty %}
     <tr>
     <td bgcolor="#e0e0e0"><b>Second Authorized person:</b></td>
     <td colspan="3">{{ loader.customer.additionalAttributes.contact_3 }}</td>
     </tr>
     {% endif %}
     {% if loader.customer.additionalAttributes.phone_3 is not empty %}
     <tr>
     <td bgcolor="#e0e0e0"><b>Second uthorized person's phone:</b></td>
     <td colspan="3">{{ loader.customer.additionalAttributes.phone_3 }}</td>
     </tr>
     {% endif %}
     <tr>
     <td bgcolor="#e0e0e0"><b>Date</b></td>
     <td style="width: 30%">{{ "now"|date("m/d/Y") }}</td>
     <td bgcolor="#e0e0e0" style="width: 10%"><b>Place</b></td>
     <td>Gorey</td>
     </tr>
     <tr>
     <td bgcolor="#e0e0e0"><b>WiFi Password</b></td>
     <td colspan="3">{{ loader.customer.additionalAttributes.wifi_pass }}</td>
     </tr>
     <tr>
     <td bgcolor="#e0e0e0"><b>Login to my BEST ISP</b></td>
     <td style="width: 30%">{{loader.customer.login}}</td>
     <td bgcolor="#e0e0e0" style="width: 10%"><b>Password to my BEST ISP</b></td>
     <td> {{loader.customer.password}}</td>
     </tr>
     <tr>
     <td bgcolor="#e0e0e0"><b>Signature</b><br>Who warrants he/she is duly authorized hereto</td>
     <td colspan="3"></td>
     </tr>
     </table>
     </div>
     <br>
     <div style="text-align: center" class="fs">(<b>"SUBSCRIBER"</b>)<br>
     (together the <b>"Parties"</b>. A reference to <b>"Party"</b> shall be a reference to one of them as so determined
     by the context.)<br>For the period and services selected below
     </div>



     <div class="fs">
     <h4><b><br>
     {% set active_services = loader.getServicesByTypeAndStatus('internet', 'active') %}
     {% for active in active_services %}
     Service: {{ active.type }}<br>
     Tarriff: {{ active.description }}<br>
     Monthly price: {{ active.unit_price }}<br>
     Service start date: {{ active.start_date }}<br>
     {% endfor %}
     {% set active_voice = loader.getServicesByTypeAndStatus('voice', 'active') %}
     {% for voice in active_voice %}
     {% if voice is not empty %}
     Service: {{ voice.type }}<br>
     Tarriff: {{ voice.description }}<br>
     Monthly price: {{ voice.unit_price }}<br>
     Service start date: {{ voice.start_date }}<br>
     {% endif %}
     {% endfor %}
     Contract Term: {{ loader.customer.additionalAttributes.contract_term }}
     </h4></b>
     </div>
     <div style="position: fixed; bottom: 0; width: 100%;" class="fs">
     <div style="text-align: right"></div>
     <hr style="width: 100%"/>
     <div>BEST ISP BROADBAND SERVICE AGREEMENT</div>
     <div style="text-align: right">Page 1 of 8</div>
     </div>
     <div style="page-break-before: always;"></div>

     <div style="text-align: justify"><h4>TERMS AND CONDITIONS FOR â€˜BEST FIBREâ€™ SERVICES</h4>
     This Subscriber Agreement (â€œAgreementâ€) is made by and between Subscriber and JS BEST ISP Limited. (â€œBEST ISPâ€), forÂ the provision and use of â€˜BRDY Fibreâ€™ Internet access (the â€œServiceâ€).
     Now therefore, in consideration of theÂ mutual promises and covenants herein contained, the adequacy of which is hereby acknowledged, and intendingÂ to be legally bound, Subscriber and BEST ISP hereby agree as follows:
     <h4>1. AGREEMENT.</h4>Subscriber agrees to be bound by this Agreement and to use the Service in compliance with the terms of thisÂ Agreement and with BEST ISPâ€™s Acceptable Usage Policy and any modifications made to same from time to time.
     <h4>2. THE SUBSCRIBER.</h4>The Subscriber is at least 18 years of age, is legally able to enter into contracts and is responsible for this SubscriberÂ account. The Subscriber shall pay all fees, taxes, charges and other expenses incurred in connection with theÂ account.
     <h4>3. SUBSCRIBER ACKNOWLEDGEMENTS REGARDING THE SERVICE.</h4>
     (a)Â The Service consists of a VDSL internet connection over a copper phone line. While BEST ISP will undertake allÂ reasonable commercial efforts to deliver the stated service the Subscriber acknowledges that service speed canÂ vary depending on distance, Internet traffic and other factors beyond the control of BEST ISP. The Service mayÂ contain material that is unsuitable for minors and The Subscriber acknowledges that BEST ISP does not and cannotÂ filter the content.
     <br>
     (b)Â The Subscriber acknowledges that in order to provide the Service, BEST ISP has contracted with communicationsÂ and network operators for internet access. The Subscriber further acknowledges that BEST ISP will only provideÂ uninterruptible continuous Service to The Subscriber pursuant to this Agreement to the extent which BEST ISP receivesÂ such service from linked communications and network operators.
     <br>
     (c) The Â Subscriber acknowledges and agrees that from time to time BEST ISP may be required to temporarily suspendÂ the Service to subscriber to verify compliance with applicable licenses, authorizations, and compliance with theÂ technical and operating parameters of the network. Under such circumstances BEST ISP will use all reasonableÂ efforts to minimize disruption to the Service including making reasonable efforts that any such suspension takeÂ place out of normal business hours.
     <br>
     (d)Â The Subscriber accepts that BEST ISP may change or withdraw any element of the Service from time to time andÂ will use all reasonable efforts to notify Subscriber of any necessary change in the Services.
     <br>
     (e) The SubscriberÂ acknowledges that the Service is an â€œalways openâ€ connection to the internet while the equipment is powered onÂ and that it is Subscriberâ€™s SOLE RESPONSIBILITY to install, configure and maintain suitable security measuresÂ to protect The Subscriberâ€™s computer and equipment from unauthorised or malicious access from the internet. AnyÂ advice or equipment provided by BEST ISP is provided â€˜as isâ€™ and BEST ISP accepts no responsibility or liability forÂ the security of Subscriberâ€™s systems.

     <div style="position: fixed; bottom: 0; width: 100%;" class="fs">
     <div style="text-align: right"></div>
     <hr style="width: 100%"/>
     <div>BEST ISP BROADBAND SERVICE AGREEMENT</div>
     <div style="text-align: right">Page 2 of 8</div>
     </div>
     <div style="page-break-before: always;"></div>
     <h4>4. EQUIPMENT.</h4>
     (a)Â From service activation BEST ISP will loan certain VDSL modem and associated equipment, hereafter termedÂ â€œEquipmentâ€, to The Subscriber to access the service. This Equipment at all times remains the sole property ofÂ BEST ISP and The Subscriber agrees to provide BEST ISP access and permission to recover said equipment on demandÂ without delay, obstruction or interference.
     <br>
     (b) The Â Subscriber agrees to use the Equipment in accordance with BEST ISPâ€™s instructions and to restrict access toÂ the Equipment to only those representatives and agents authorized by BEST ISP. The Subscriber agrees to takeÂ reasonable steps to protect the Equipment from damage, loss or theft.
     <br>
     (c)Â The Subscriber agrees to notify BEST ISP as soon as reasonably possible once he becomes aware of any damageÂ to the equipment or defect in the operation of the equipment by telephoning or emailing BEST ISP at the numbersÂ or addresses published from time to time, or office@bestisp.com
     <br>
     (d)Â On termination or cancellation of the Service Contract for any reason whatsoever, it is the responsibility of theÂ Subscriber to return by recorded mail in good condition and suitably packaged, the VDSL Modem and any otherÂ related equipment provided by BEST ISP. Failure to return equipment within 14 days of the serviceÂ termination/cancellation date will generate an automatic equipment fee of â‚¬99 including VAT which will beÂ deducted from The Subscribers account and The Subscriber hereby agrees to same.
     <br>
     <h4>5. TERM.</h4>
     (a)Â This Agreement is for an initial term of 6, 12 or 18 months, as defined by your price plan rules, and shallÂ automatically renew for subsequent month term, until terminated in accordance with this Agreement. After theÂ Initial Term, The Subscriber may terminate this Agreement upon thirty (30) days written notice to BEST ISP.
     <br>
     (b)Â Should The Subscriber terminate this agreement for any reason during the initial term, a cancellation fee equal toÂ the remainder of the contract term will become immediately due, and The Subscriber acknowledges and agrees toÂ pay such fee and return any equipment provided.
     <br>
     (c)Â The Subscriber may upgrade the service at any time to a higher service and accepts that a new contract appliesÂ from the date the upgrade is applied.
     <br>
     (d)Â BEST ISP may in its sole discretion terminate this Agreement at any time. In the event that BEST ISP terminatesÂ this Agreement for reasons other than breach of this Agreement by Subscriber, then BEST ISP shall endeavour toÂ the extent reasonably possible to provide 30 days notice to The Subscriber. The Subscriber is liable under this AgreementÂ for all fees and charges until such time as the Agreement has been terminated. THE SUBSCRIBER UNDERSTANDS THAT UNLESS WRITTEN NOTIFICATION IS RECEIVED BY BEST ISP AFTER THE INITIAL TERM, THEÂ SERVICE SHALL CONTINUE AND SUBSCRIBER WILL CONTINUE TO BE RESPONSIBLE FOR PAYMENTÂ OF APPLICABLE SERVICE FEES.
     <br>
     <div style="position: fixed; bottom: 0; width: 100%;" class="fs">
     <div style="text-align: right"></div>
     <hr style="width: 100%"/>
     <div>BEST ISP BROADBAND SERVICE AGREEMENT</div>
     <div style="text-align: right">Page 3 of 8</div>
     </div>
     <div style="page-break-before: always;"></div>
     <h4>6. TERMINATION.</h4><br>
     (a)Â If Subscriber is dissatisfied with the Service or any related terms, conditions, rules, policies, guidelines, orÂ practices, and if these issues cannot be resolved through BEST ISPâ€™s Customer Complaints procedure,Â The Subscriberâ€™s sole remedy is to discontinue using the Service, cancel the account, and pay any cancellation feesÂ that apply. To cancel the Service The Subscriber must send a written request for termination by email to BEST ISPÂ and same must be signed by an authorised representative of The Subscriber to arrive not less than 5 working daysÂ before the end of the current billing term. Should The Subscriber terminate this agreement during the initial term forÂ any reason other than a failure by BEST ISP to provide Internet Access service for a period in excess of 5 days, aÂ cancellation fee equal the remainder of the contract term will become immediately due, and The SubscriberÂ acknowledges and agrees to pay such fee.
     <br>
     (b)Â Upon cancellation or otherwise upon termination of this Agreement, related email and hosting services will beÂ terminated and all the Subscriber files stored on BEST ISP servers may be deleted. BEST ISP may terminate thisÂ Agreement, your password, your account, or your use of the Services for any reason, including, without limitation,Â if BEST ISP, in its sole discretion, believes you have violated the Agreements or if The Subscriber fails to pay anyÂ charges when due.
     <br>
     (c)Â Sections 11, 20, 21, and 22 of this Agreement shall survive termination of this Agreement.
     <br>
     (d)Â BEST ISP may terminate this agreement immediately if The Subscriber is subject to bankruptcy, insolvency,Â examinership, receivership, liquidation or any similar proceedings, or in BEST ISPâ€™s exclusive opinion is unable toÂ pay fees due to BEST ISP.
     <br>
     <h4>7. FEES AND PAYMENT</h4><br>
     (a)Â Subscriber shall pay a monthly service fee and all other applicable fees, charges, taxes, and other amountsÂ for the Service at the rates in effect for the current billing period. BEST ISP may increase or decrease the monthlyÂ service fee. BEST ISP will use all reasonable efforts to provide The Subscriber thirty (30) days or more notice of same.Â If such changes to the basic monthly service fee are to The Subscribers detriment (e.g. a price increase), The SubscriberÂ may terminate this agreement by giving thirty (30) days written notice, and The Subscriber will remain liable only forÂ any balance on the account.
     <br>
     (b)Â Payment is due in full by Credit Card or Direct Debit at the start of each billing month. All charges areÂ considered valid unless disputed in writing within thirty (30) days of the billing date. Adjustments will not be madeÂ for charges that are more than 30 days old. If any payment is more than 7 days overdue or is returned by theÂ bank unpaid, the Service may be suspended with immediate effect and remain suspended until the due amountsÂ are paid in full. The Subscriber is not relieved of the obligation to pay the monthly service fee while an account isÂ suspended. BEST ISP may at its sole discretion terminate the Service and this Agreement for any accounts whichÂ are 14 days or more overdue. A reactivation fee or deposit may be required before Service is reactivated afterÂ suspension or termination. Credit account balances shall not accrue interest. The Subscriber agrees to pay theÂ reasonable costs of any collection agency, solicitor or court used by BEST ISP to collect past due amounts or toÂ enforce this Agreement. Returned cheques or Direct Debits will incur a â‚¬5 administration fee.
     <br>
     (c)Â A â‚¬1.50 inclusive of VAT charge applies to all bills for non-Direct Debit customers.(d)Â Where a package is downgraded within contract, a â‚¬30 inclusive of VAT downgrade fee applies.
     <br>
     <div style="position: fixed; bottom: 0; width: 100%;" class="fs">
     <div style="text-align: right"></div>
     <hr style="width: 100%"/>
     <div>BEST ISP BROADBAND SERVICE AGREEMENT</div>
     <div style="text-align: right">Page 4 of 8</div>
     </div>
     <div style="page-break-before: always;"></div>
     <h4>8. SUBSCRIBER ACCOUNT.</h4><br>
     <br>(a)Â The Subscriber will receive a username, password, account reference, and various other account details.Â The Subscriber is solely responsible for use of the Service and for ensuring their information is kept confidential.Â The Subscriber must notify BEST ISP immediately upon discovering any unauthorized use of their account.
     <br>(b) The Â Subscriber acknowledges that usernames, passwords and IP addresses may change or be changed fromÂ time to time, and specifically that fixed IP addresses are not guaranteed except in the case of custom servicesÂ where this specifically comprises part of the service contract.
     <br>
     <h4>9. FAIR ACCESS POLICY.</h4><br>
     To ensure equal Internet access for all subscribers, BEST ISP operates a fair access policy. Fair accessÂ establishes an equitable balance in Internet access across high speed Internet services for all subscribers. ToÂ ensure this equity, certain types of traffic such as email and browsing may be prioritized over other traffic.Â BEST ISP provides the Service on a â€œbest effortâ€ basis and does not guarantee upload or download speeds.Â
     <br>
     <h4>10. CUSTOMER COMPLAINT POLICY.</h4><br>
     Should you be dissatisfied for any reason with the service provided by BEST ISP, a formal complaint process isÂ provided to ensure that your issue is addressed as quickly as possible and at the highest level necessary. This isÂ outlined as follows:
     <br>
     (a)Â GENERAL: If you have a general complaint regarding BEST ISP, email full details and your account referenceÂ us at office@bestisp.com. Issues registered in this way automatically enter BEST ISPâ€™s complaint trackingÂ systems, ensuring the most appropriate and quickest handling.
     <br>
     (b)Â BILLING: If you have a billing enquiry or complaint, please contact the Accounts Department via the numberÂ shown on your invoice/statement, or by email to office@bestisp.com.
     <br>
     (c)Â WRITTEN: If you would prefer to put your complaint in writing, we will respond to your letter by telephone andÂ will confirm any details in writing should you wish. Your letter should be addressed to: Best ISP, Main street Gotham city
     <br>
     (d)Â IDENTITY: If telephoning BEST ISP, each staff contact receiving your call will provide his or her name onÂ request. Record same for future reference or to revert later to the same person working on your query orÂ complaint.
     <br>
     (e)Â RESOLUTION: The staff member receiving your call will either resolve your complaint or transfer yourÂ complaint to a more appropriate person to endeavour to resolve your complaint to your satisfaction. WhereÂ possible, our staff will resolve your concern at the first point of contact.
     <br>
     (f)Â ESCALATION: If you are not satisfied with the resolution, or if you feel that you have not received a fairÂ hearing, your complaint can be escalated to a manager on your request. He or she will review yourÂ complaint and resolutions offered and discuss the complaint with you.
     <br>
     <div style="position: fixed; bottom: 0; width: 100%;" class="fs">
     <div style="text-align: right"></div>
     <hr style="width: 100%"/>
     <div>BEST ISP BROADBAND SERVICE AGREEMENT</div>
     <div style="text-align: right">Page 5 of 8</div>
     </div>
     <div style="page-break-before: always;"></div>
     <h4>11. INSTALLATION.</h4>
     (a)Â The installation, use, inspection, maintenance, repair, and removal of the equipment may result in serviceÂ outage or potential damage to your computer. The Subscriber is solely responsible for backing up all existingÂ computer files and data. BEST ISP and its employees, agents, contractors, and representatives shall have noÂ liability whatsoever for any damage to or loss or destruction of any of your hardware, software, files, data, orÂ peripherals.
     <br>
     (b)Â BEST ISP will endeavour to provide the Service to all eligible applicants, subject to technical and commercialÂ feasibility. BEST ISP may in its sole discretion determine that it cannot or will not service a particular site orÂ subscriber, and reserves the right to cancel the installation process and refund any money that The Subscriber hasÂ paid. BEST ISP will notify you of its intent to cancel as soon as reasonably possible. It may take up to 90 or moreÂ days to determine if BEST ISP is able to provide service in certain locations. BEST ISP shall have no responsibilityÂ whatsoever for claims arising out of its failure or refusal to complete the installation or provide the Service.
     <h4>12. COPYRIGHTS AND LICENSES.</h4>
     The content on the Service is protected under applicable copyright law. Any copying, modification, distribution,Â publication or other use by The Subscriber, or by any user of The Subscriberâ€™s account, of any such content is prohibited,Â except as expressly permitted by the holder of the applicable copyrights.
     <h4>13. NO ENDORSEMENT.</h4><br>
     BEST ISP does not endorse or in any way vouch for the accuracy or completeness of any content made availableÂ through the Service. BEST ISP does not recommend that such content be relied on by The Subscriber withoutÂ appropriate verification.
     <h4>14. SUBSCRIBER CONDUCT.</h4>
     The Subscriber shall comply with all laws, rules, regulations and legal obligations related to the Service and with allÂ acceptable use policies and procedures established from time to time by BEST ISP. The Subscriber shall not use theÂ Service to conduct any business or activity or to solicit the performance of any activity which is prohibited by anyÂ law, rule, regulation or legal obligation. The Subscriber shall not intercept email in an unauthorized manner or engageÂ in â€œspammingâ€ or any similar conduct.
     <h4>15. THIRD PARTY ACCESS</h4>
     (a)TheÂ Subscriber shall not resell, share, lease, hire or otherwise permit access to the Service to any third party,Â including but not limited to the connection of any third party to the Service through use of direct cable connection,Â network connection, wireless networking, or any other means.
     <br>
     (b)Â BEST ISP reserve the right to suspend the Service pending investigation where it reasonably suspects theÂ above clause is breached by The Subscriber and reserves the right to terminate with immediate effect the Service andÂ this Agreement where such breach has taken place.
     <div style="position: fixed; bottom: 0; width: 100%;" class="fs">
     <div style="text-align: right"></div>
     <hr style="width: 100%"/>
     <div>BEST ISP BROADBAND SERVICE AGREEMENT</div>
     <div style="text-align: right">Page 6 of 8</div>
     </div>
     <div style="page-break-before: always;"></div>
     <h4>16. SERVICE MONITORING.</h4><br>
     BEST ISP has no obligation to monitor the Service, but may do so and disclose information regarding use of theÂ Services for any reason if BEST ISP, in its sole discretion, believes that it is reasonable to do so, including to:Â satisfy laws, regulations, or governmental or legal requests; operate the Service properly; or protect itself and itsÂ subscribers. BEST ISP may immediately remove your material or information from BEST ISP servers, in whole or inÂ part, which BEST ISP, in its sole and absolute discretion, determines to infringe anotherâ€™s property rights or toÂ violate BEST ISPâ€™s Acceptable Use Policy.
     <br>
     <h4>17. SUBSCRIBER EQUIPMENT.</h4><br>
     The Subscriber shall maintain and operate suitable and fully compatible terminal equipment and communicationÂ devices required to access the service. BEST ISP makes no representation or warranties, either express or implied,Â regarding such Subscriber equipment.
     <br>
     <h4>18. DISCLAIMER OF WARRANTIES.</h4><br>
     Access to the service is not guaranteed. The Service is distributed on an â€œas isâ€ and â€œas availableâ€ basis without warranties of any kind, either express or implied, including but not limited to warranties of title or impliedÂ warranties of merchantability or fitness for a particular purpose or otherwise.
     <br>
     <h4>19. LIMITATION OF LIABILITY.</h4><br>
     Neither BEST ISP nor any of its information or content providers, service providers, licensors, employees or agentsÂ shall be liable for any direct, indirect, incidental, special, punitive or consequential damages arising out of TheÂ Subscriberâ€™s use of the service or inability to use the service or any breach of any representation or warranty. InÂ any event, no such liability shall exceed the total amount actually paid by The Subscriber for services provided underÂ this agreement for the prior six month period.
     <br>
     <h4>20. INDEMNITY.</h4><br>
     The Subscriber assumes all risk and liability for any use of the Service. The Subscriber agrees to indemnify BEST ISPÂ against all claims, liability, damages, costs and expenses, including but not limited to reasonable legal fees,Â arising out of or related to Subscriberâ€™s use of the Service.
     <br>
     <div style="position: fixed; bottom: 0; width: 100%;" class="fs">
     <div style="text-align: right"></div>
     <hr style="width: 100%"/>
     <div>BEST ISP BROADBAND SERVICE AGREEMENT</div>
     <div style="text-align: right">Page 7 of 8</div>
     </div>
     <div style="page-break-before: always;"></div>
     <h4>21. THIRD PARTY BENEFICIARIES.</h4>
     The provisions of Sections 18, 19 and 20 are for the benefit of BEST ISP and its respective contractors, informationÂ or content providers, service providers, licensors, employees and agents; and each shall have the right to assertÂ and enforce such provisions directly on its own behalf.
     <h4>22. SUPPORT SERVICES.</h4>
     The Subscriber shall direct all enquiries and service related issues to BEST ISPâ€™s Customer Sales and Support contact points, as defined on its website from time to time or directly by email to office@bestisp.com.
     <h4>23. APPLICABLE LAWS.</h4>
     This Agreement shall be governed by the laws of the Republic of Ireland. Any cause of action of The Subscriber, or byÂ users of The Subscriberâ€™s account, with respect to the Service or this Agreement must be instituted within six (6)Â months after the claim or cause of action has arisen or be barred. It is acknowledged that this is a services contract and not a contract for the sale of goods.
     <h4>24. GENERAL.</h4>
     (a)This Agreement constitutes the entire agreement between the parties relating to the subject matter hereunder,Â and supersedes any and all oral and/or written statements, discussions, representations and agreements madeÂ by either party to the other, and may not be assigned without the express written consent of BEST ISP. NoÂ modification of this Agreement shall be binding on either party unless it is in writing and signed by both parties.Â Failure on the part of BEST ISP to enforce any provision of this Agreement shall not be construed as a generalÂ waiver or relinquishment of the right to enforce such provision. If any provision shall be held unenforceable, theÂ validity legality and enforceability of the remaining provisions shall in no way be affected thereby, and the intentÂ of the unenforceable provision enacted to the maximum enforceable extent.
     <br>
     (b)Â Publicity. BEST ISP may identify The Subscriber as a user of BEST ISPâ€™s services in reports, advertisements and otherÂ promotional literature or forms of publication. The Subscriber should advise BEST ISP in writing if it does not wish to beÂ identified.
     <br>
     (c)Â These Terms and Conditions may be modified by BEST ISP from time to time, the current and applicableÂ version always being available in electronic form from the relevant section of the BEST ISP website atÂ www.wi.ie. BEST ISP will make reasonable attempts by email or other communication, including but notÂ limited to national press, to inform The Subscriber when the Terms and Conditions of the Service are amended.Â Should any modification cause a reasonable deterioration in the level of the Service the Subscriber couldÂ reasonably expect, their sole remedy is to terminate service in writing within 30 days of such change. ShouldÂ The Subscriber continue to use the Service 30 days following date of notice of an amendment made to the Terms andÂ Conditions the Subscriber is deemed to have accepted the amended terms.
     <br>
     (d)Â Headings for Convenience. All headings preceding paragraphs and subparagraphs have been inserted forÂ convenience of reference only, and shall not be relied upon in determining the meaning of the rights andÂ obligations of BEST ISP or Subscriber.
     </div>
     <div style="position: fixed; bottom: 0; width: 100%;" class="fs">
     <div style="text-align: right"></div>
     <hr style="width: 100%"/>
     <div>BEST ISP BROADBAND SERVICE AGREEMENT</div>
     <div style="text-align: right">Page 8 of 8</div>
     </div>
     </body>
     </html>
     ```
</div>
</details>
