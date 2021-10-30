# Unreal Marketplace Vault Exctractor

A script that generates a Markdown list of your [Unreal Marketplace](https://www.unrealengine.com/marketplace/en-US/store) [Vault](https://www.unrealengine.com/marketplace/en-US/vault), plus some random stats (e.g. total value).

## Requirements

* Python 3

## How to use

Since your Vault is secured, the script can't request its data from Epic by itself. It requires some user input to get this data first.

This is done by accessing the Marketplace API with your browser, and manually saving the results.

* Open your web browser
* Log into the [Marketplace](https://www.unrealengine.com/marketplace/en-US/store)
* Open [this link](https://www.unrealengine.com/marketplace/api/assets/vault?lang=en-US&start=0&count=100) in your browser
* `Right click` the page > `Save As...` and save the `.json` file on the Vault Extractor `data/` folder

The Marketplace API only allows requesting Vault data by batches of 100 items, so if you have more than that, you'll have to repeat the procedure above multiple times, and therefore save multiple `.json` files. Below are the links to extract data by batches of 100, so use them according to your Vault size.

* [0-100](https://www.unrealengine.com/marketplace/api/assets/vault?lang=en-US&start=0&count=100)
* [100-200](https://www.unrealengine.com/marketplace/api/assets/vault?lang=en-US&start=100&count=100)
* [200-300](https://www.unrealengine.com/marketplace/api/assets/vault?lang=en-US&start=200&count=100)
* [300-400](https://www.unrealengine.com/marketplace/api/assets/vault?lang=en-US&start=300&count=100)
* [400-500](https://www.unrealengine.com/marketplace/api/assets/vault?lang=en-US&start=400&count=100)
* [500-600](https://www.unrealengine.com/marketplace/api/assets/vault?lang=en-US&start=500&count=100)
* [600-700](https://www.unrealengine.com/marketplace/api/assets/vault?lang=en-US&start=600&count=100)
* [700-800](https://www.unrealengine.com/marketplace/api/assets/vault?lang=en-US&start=700&count=100)
* [800-900](https://www.unrealengine.com/marketplace/api/assets/vault?lang=en-US&start=800&count=100)
* [900-1000](https://www.unrealengine.com/marketplace/api/assets/vault?lang=en-US&start=900&count=100)

Once you've saved all the necessary `.json` files to the `data/` folder, simply run `mp_vault_extractor.py`. The process might take a while (~1s/product) as it needs to further request the Marketplace API for each product.

After the process has finished, you'll find a `mp_vault_list.md` at the root of the project, which the list of all your Marketplace Vault products, plus some basic stats.