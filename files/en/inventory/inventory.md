Inventory
==========


Inventory is a built-in feature that allows you to store and account information about equipment and other products. It stores the information about your suppliers and product vendors.


Inventory includes:
* **Vendors** - vendors of your products.
For example: «TP-Link».
It is not necessary to specify the vendor for the product.

* **Products** - your products.
For example: «TP-Link TL-WR841N».

* **Items** - items of a specific **product**.
For example: «TP-Link TL-WR841N» with serial number 00-11-22-33. You can manage each item. You can sell or rent items to your customers. Or you can mark them for internal usage.

* **Suppliers** - suppliers of your **products**. For example: «Super shop».

* **Supplier invoices** - they are used to add **items** of **products** to the system.


## Vendors

In menu – `Inventory/Supply/Vendors`
![Vendors](vendors.png)

You can create new vendor via button «Add vendor»
![Add vendor](add_vendor.png)
Type the name of the vendor and press «Add»



## Products
`Inventory/Products`

![Products](products.png)

You can create new product via button «Add Product»

![Add product](add_product.png)

* **Name** – the product’s name
* **Vendor** – the vendor of the product. (Not necessary)
* **Photo** – the product’s photo. You can choose a photo and it will be added to the product. It will appear in the list of products and in the list of items (near items of this product)
* **Sell price** – the default price for the sale of this product to customers.
* **Rent price** – the default price for the rent of this product to customers.



## Suppliers
`Inventory / Supply / Suppliers`
![Suppliers](suppliers.png)

You can create new supplier via button *«Add supplier»*
![Add supplier](add_supplier.png)

Only field **«Name»** is required.
* **Tax included** – include VAT% in supplier’s invoices.


## Supplier invoices

`Inventory/Supply/Supplier Invoices`
![Supplier invoices](supplier_invoices.png)


If you want to add product items – you have to add it via creating «supplier invoice» here.

Press «Add invoice» and fill invoice fields.
![Create invoice](add_supplier_invoices.png)


* **Supplier** – choose a supplier. This is obligatory.
* **Supplier invoice number** – Invoice number from supplier. (Not necessary)
* **File** – if you have invoice file (an image or a document) you can specify it here. It’ll be downloaded in the system while invoice is creating. Afterwards you can view or download it for your needs.
* **Product** – choose an existing product. Or you can type new product name and product will be created automatically.
* **Quantity** – items count to add to the system
* **Price** – purchase price of this items.


---
If you press «Add» invoice – the new window will appear. There you can add barcodes of the items. (You can edit barcodes later by pressing <icon class="image-icon">![Barcode](barcode_icon.png)</icon> )
![Add barcode](add_barcode.png)

After creating invoice – items of selected products will be added to the system. They will have status **In stock**

---

# **Items** (of products)

`Invertory/Items`


  This is the place where you can see information of the items of your products, manage them and add new ones.

  ![Items](items.png)

  To add a new item just press the button "Add" and select the needed option for one or multiple items.
  ![Add Items](add_items.png)
  ![Add items box](add_items_box.png)

  You can edit some additional information or edit existing here. Press edit button for this.

  ![Edit item](edit_item.png)

  If you add some photo for the item, it will override a «global» photo of a product (if product has it).

  If you want to manage some item(s) – you have to check it <icon class="image-icon">![Checkbox](checkbox_icon.png)</icon> and press the **"Actions"** button <icon class="image-icon">![Action button](action_button.png)</icon> to select one of the desired options.
  ![Manage items](manage_items.png)


* **Internal usage** – the item is used by your organization

  ![Internal usage](internal_usage.png)

* **Sell** – sell the item to the customer

  ![Sell](sell.png)

  Choose the customer and the invoice will be generated. Edit what you need and press «Sell»

* **Rent** – rent the item to the customer
Before you can rent some item to the customer – you must create a custom service for this! (`Tariff plans/Custom/Add plan`)
![Create plan](create_plan.png)

  Then to rent some item – go to the items, check it, press «Rent» in the section "Actions" <icon class="image-icon">![Action button](action_button.png)</icon>
  ![Rent service](items_rent_1.png)
  ![Create service](items_rent_2.png)

  1. Choose the customer;
  2. Select rent plan;
  3. Edit the rest fields for your needs, press «Rent»

  Rent service will be added for selected customer (in Custom services)


* **Return** – return the item to the stock

  You can return the item to the stock only if it has status «in usage» (rent, sold, internal usage)

  Select item(s), press «Return»

  ![Return](return.png)

  You can select status (In stock, Returned ) and mark item (New, Broken)

  All possible statuses of item: `In stock, Internal usage, Sold, Rent, Returned`
  You can see every item’s history. To do this press history button <icon class="image-icon">![History](history_icon.png)</icon>.


## Customers

When you rent or sell your products to customers you can see it in customer info
![Customer](customer.png)

If you rent some item – customer can see it at the portal (in the section "Services")
![Custom service](custom_service.png)

Also, you can see the video description of Inventory feature in use:
<iframe frameborder=0 height=270 width=350 allowfullscreen src="https://www.youtube.com/embed/KY_Qq-1VxMg?wmode=opaque">Video on youtube</iframe>
