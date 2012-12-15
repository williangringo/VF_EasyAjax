# VF_EasyAjax Module

Allows frontend developers send ajax requests for every page and get Json response.  
You don't need to work with app/code section of Manento and change any PHP code.  
Make all what you need works via Ajax using only layout xmls, theme templates and javascript.  

In the Json response frontend developers can receive:
* All messages that were added to session
* Some blocks from current page layout
* Any block that should be added to special layout xml
  
# How to use:  
  
For any page url add easy_ajax=1 and this page returns json instead of html.  
It returns:  
1. messages: [{type: , code: }] if on this page some message is added to any session model.  
2. action_content_data: {} if you add to params action_content[] with block names
  
# Example  
  
For add product to cart via Ajax use default add to cart url and add this params:  
* easy_ajax: 1  
* action_content[0]:cart_sidebar  
* action_content[1]:top.links  

You will get json response with 
* messages: [{type: 'success', code: 'Massage that product was successfully added to cart.'}]  
* action_content_data: {cart_sidebar: "\<div ... \</div>", top.links: "\<ul ... \</ul>"}  
  
So with response data you can simple update needed blocks: 
* cart_sidebar with items recently added to cart
* top.links with count of items near link to My Cart