# Whitelist and Royalty Options

#### Whitelist <a href="#whitelist" id="whitelist"></a>

A whitelist is a collection of addresses that are eligible to mint in stages prior to a public mint beginning for a collection. Whitelisted addresses can be granted a variety of permissions:

They can mint tokens from a collection

* At reduced prices defined by the creator
* Before the start time
* At a quantity defined by the creator
* In up to 3 stages with different prices and member lists

Using Stargaze Studio you can provide a whitelist and specify their permissions.&#x20;

You can set the following information:

* Unit Price: Token price for whitelisted addresses.&#x20;
* Member Limit: Maximum number of whitelisted addresses.
* Per Address Limit: Maximum number of tokens a whitelisted address can mint
* Start Time: Start of minting time for whitelisted addresses
* End Time: End of minting time for whitelisted addresses
* Whitelist File: The txt file that contains whitelisted addresses.
* The start and end time for whitelisted minters must be before the public start time.
* The whitelist file is a simple .txt file where each line consists of one Cosmos address.&#x20;

<figure><img src="../../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

The above 1 stage whitelist is configured to allow the 3 listed addresses to mint from a collection at the price of 1 ATOM, a maximum of 2 mints per address, and will remain open for 24 hours. When the whitelist concludes, the public mint phase stars.

**Whitelist Stages**

Whitelists can be arranged in up to 3 stages with different unit prices and address mint limits in each. Different addresses can be added to each stage, providing creators with a robust tool for rewarding select community members with early access to mints and other launch structures.

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

* Addresses for each stage should be arranged in separate files prior to upload.
* Stages are arranged dictated by time, with the start of stage 1 dictating the start of stage 2 and so on. **The end of the final stage dictates the start of the public mint phase.**
* When instantiating the contract, the total number of addresses from all stages cannot exceed 10,000. More addresses up to 30,000 can be added as an execution on the whitelist contract afterward in Studio at https://studio.stargaze.zone/contracts/whitelist/execute

## Royalties

Royalties are payments that are transferred to an address every time an NFT from that collection is sold in the marketplace. You only need to set two parameters:

* **A payment address** that will receive the funds
* **The** **share percentage** you want from each sale

If you are done with the configurations, press the **Create Collection** button and sign the pop-up transactions.

Unlike the previous section, you will receive **two different transactions** to sign. The first one is to instantiate the whitelist contract and the second one is to publish the collection.

An info box will appear at the top of the page when the transactions are confirmed, including your minter contract, CW721 contract, and whitelist contract. Save these for reference as they are required for performing actions such as updates to your collection or whitelist.

Congrats! You have successfully learned how to create a collection with whitelist and royalty configurations.Your collection page
