# Shops

Shops are pages from which users can spend [currency](currencies.md) to purchase [items](items.md). They can be edited in the admin panel by users with the **Edit World Data** [power](user-ranks.md).

## Usage

Shops listed on the shop index can be clicked to view the shop's contents, including the shop image, flavour text and shop stock.

Shop stock is categorised by the items' item categories. Each item lists:

- Item name
- Cost and currency
- Available stock (if applicable)
- Purchase limit (if applicable)

Note that items with 0 stock are still listed in the shop.

Clicking on the item brings up the purchase modal. If the item can be purchased, the user is given the option to purchase the item.

The option to use the user's bank or a character's bank may be provided. In the latter case, a character's code (must be owned by the user) can be entered, and currency will be deducted from the character's bank instead. The item is deposited in the user's inventory, and the code of the purchasing character is noted in the item's source information. This makes it possible, for example, to have users purchase items for design updates that must be used specifically on the character that purchased it.

A purchase log is available for every user, linked in the shops sidebar, as a quick reference for their own recent purchases.

## Editing

Shops have the following properties:

- Name
- Shop Image
- Description (accepts HTML)
- Set Active

**Name** is the name of the shop, as shown in the shop index and on the shop's page.

The **Shop Image** is the image used to represent the shop on the shop index and is also displayed at the top of the shop's page.

**Description** is displayed underneath the shop image on the shop's page. It can be used, for example, to provide helpful information about the shop, or add additional flavour text.

**Set Active** affects whether or not the shop is visible on the shop index. If set to false, it will not be shown on the shop index and cannot be accessed by anyone.

Shop display order can be edited on the admin panel shop index page.

### Shop Stock

Shop stock is editable after a shop is created. Each shop stock has the following properties:

- Item
- Cost (quantity and currency)
- Use User Bank
- Use Character Bank
- Set Limited Stock
    - Quantity
- User Purchase Limit

**Item** is the item to be sold. Only items can be sold in shops.

**Cost** is the price of the item. A value and currency must be selected.

**Use User Bank** and **Use Character Bank** determine if the user has the option to use either for purchase. For the item to be purchasable, the bank type has to correspond to whether users and/or characters can own that currency. (e.g. If a user cannot own the currency but only "Use User Bank" is enabled, the item cannot be purchased at all from the shop.)

**Set Limited Stock** and **Quantity** allows only a specific amount of the item to be made available for purchase. The quantity will go down as items are purchased from the shop. As mentioned above, items with 0 quantity will still be displayed in the shop as an indicator that the item was purchased, but is now sold out. If limited stock is not enabled, the item will have infinite stock.

**User Purchase Limit** limits the number of that stock the user can purchase from that particular shop. The limit cannot be circumvented - even if the stock record is deleted and the item is re-added to the shop, the limit still applies. However, if the same item is added to a different shop, it can be purchased.

## See Also

- [Items](items.md)
- [Currencies](currencies.md)