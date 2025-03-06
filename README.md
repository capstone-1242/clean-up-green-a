# clean-up-green-a - Fantastic Five (Alec, Audrey, Liam, Madison,and Simran)

# Shopify Theme Development Instructions

### Store Information
- **Store Name**: Cleanup Green  
- **Store URL**: [https://cleanup-green.myshopify.com/](https://cleanup-green.myshopify.com/)
- **Password**: maiwul

## useful commands
 1. shopify theme dev -e development
  >> use this command to work in local environment(shopify.theme.toml file is required to use this)
  2. shopify theme dev  (alternative, if first doesn't work)
   ## Use the following command to push your theme changes to the main website:
      shopify theme push --store cleanup-green

## Theme Push Process

Here is an image showing how to push changes to your live Shopify theme:

![screenshot](screenshot.png)

Follow the steps below to push your changes:
1. Use `shopify theme push --store your-store-url` to push changes.
2. Select the LIVE > DAWN theme to update the live store.


### What's New:
- **Upload images**: Do not upload images into the assets folder, instead upload them to `contents > files` on the main website
- **Use Upload images**: To use images uploaded to the files , you can reference them using the {{ file_url }} filter.
- ---> <img src="{{ 'example-image.jpg' | file_url }}" alt="Example Image">


## Rendering Sections in Shopify Liquid vs JSON

### 1. **Rendering Sections in Liquid Files**

In Shopify, sections are rendered within Liquid templates using the `section` tag. This allows you to dynamically include and display content sections defined in your theme.

# Example in Liquid:

If you have a section called `hero-banner.liquid` in your `sections` directory, you can render it in a Liquid template like this:

```liquid
{% section 'hero-banner' %} 

# 2. Rendering Sections in JSON Files
Sections can also be referenced in Shopify's JSON templates, which are used in Shopify's Online Store 2.0. JSON files are used for creating theme layouts, and sections are defined in the sections array.

Example in JSON:
In the index.json file, sections are referenced like this:

json
Copy code
{
  "sections": {
    "hero-banner": {
      "type": "hero-banner",
      "settings": {
        "heading": "Welcome to our Store!"
      }
    }
  },
  "order": ["hero-banner"]
}

### Summary:
- **Liquid Rendering**: Sections are rendered using `{% section 'section-name' %}`.
- **JSON Rendering**: Sections are defined in the JSON file with the `sections` key, and the `order` key controls the sequence of sections.
- **Difference**: Liquid renders the section immediately in the template, while JSON defines the sections and their layout order for Online Store 2.0 templates.


