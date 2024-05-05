## Digital gift cards:

When customers order a digital gift card on Shopify, after the order is created, Shopify immediately auto fulfills the order, assigns a serial number to digital gift card, loads the value to activate the gift card and consequently, when HotWax Commerce downloads that order from Shopify, it is automatically marked as “Completed”.

Customers receive the gift card in their registered email along with the serial number that can be used to redeem the gift card.

## Physical gift cards:

Orders with physical gift cards are not auto-fulfilled in Shopify. Therefore, HotWax Commerce routes them through the traditional fulfillment process.

# Fulfillment of Gift Cards in Store

After physical gift cards are allocated, HotWax Commerce begins syncing them to systems that are responsible for fulfillment of those items. In the event where gift cards are allocated to a store for fulfillment, they show up in the HotWax Store Fulfillment App.

As part of the fulfillment process, store associates assign a unique serial number to each gift card and load the corresponding value onto it. This ensures that when customers receive their orders, they can easily redeem the value by using the serial number provided on the gift card.

The fulfillment update for gift card orders, along with tracking details, is synchronized to Shopify using the `Completed Orders` job.

{% hint style="info" %}
It’s crucial to note that the gift cards are not functional until they are activated on Shopify. The activation process in Shopify is a necessary step to ensure that the gift cards are redeemable and fully functional upon receipt by customers.
{% endhint %}

## Activation of Gift Cards

In the activation process, store associates directly apply a unique serial number and load the corresponding value onto the gift card in Shopify POS. This activation step ensures that the gift card is fully functional.

{% hint style="info" %}
Digital gift cards are auto-activated and customers can directly redeem them by entering a unique serial number provided with the card.
{% endhint %}

# Fulfillment of Gift Cards in Warehouse

When the fulfillment location where a gift card item is allocated leverages NetSuite for fulfillment, usually a warehouse, then the HotWax Commerce syncs those items' allocation with NetSuite.

Learn more about fulfillment in NetSuite

## Activation of Gift Cards

Similar to how store associates assign serial numbers and load values onto gift cards in-store, warehouse fulfillment teams also undertake these tasks to prepare gift card orders for shipment.

HotWax Commerce Integration Platform retrieves gift card items, their assigned serial numbers, and corresponding values from NetSuite and generates a JSON file. Subsequently, it calls the Shopify API to request activation for the gift card. 

Once the gift card is activated on Shopify, customers can conveniently redeem it.