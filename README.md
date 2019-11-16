ajaxify-cart
============

From your Shopify admin, go to Online Store > Themes.

Find the theme you want to edit, and then click Actions > Edit code.

In the Layout directory, click theme.liquid.

Ajax cart
Find the closing </body> tag. On a new line right above the closing </body> tag, paste the following code:

{% render 'ajaxify-cart' %}
Ajax cart 2
Click Save.

In the Snippets directory, click Add a new snippet:

Add a new snippet
Name your snippet ajaxify-cart, and click Create snippet:

ajaxify-cart snippet
Your new snippet will open in the code editor.

In your new ajaxify-cart.liquid file, paste this code hosted on GitHub.

Caution
In the pasted code, replace all instances of .size() with .length. The .size() method is depreciated as of JQuery 1.8.

Click Save.

Debut
If you use Debut, then continue to the next steps:

In ajaxify-cart.liquid, find the opening <script> tag at the top of the file. On a new line right below the opening <script> tag, paste the following code:

window.onload = function() {
Find the closing </script> tag. On a new line right above the closing </script> tag, paste the following code:

}
In the same file, find the following code:

cartCountSelector:             '.cart-count, #cart-count a:first, #gocart p a, #cart .checkout em, .item-count',
Replace it with:

cartCountSelector:             '#CartCount',
Click Save.

In the Sections directory, click header.liquid.

Find the following code:

{% if cart.item_count > 0 %}
Replace it with:

{% if cart.item_count > -1 %}
Click Save.
