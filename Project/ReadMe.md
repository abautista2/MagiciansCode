Magician's Code (Shopping Cart)

Group: 71
Name:
SUKHJIT-SINGH (13051850),
Limbu Utsab (13042692),
Bautista, Arvie Adrian S. (13072580)

Application Link:


*********************************************
# Login
In the login page, each user can log in to view their shopping cart.

Each user has a userID and password;
[
	{name: admin1, password: admin1},
	{name: admin, password: password},
	{name: houdini, password: abracadabra}
]

If the user does not have a shopping cart in the database, they will have to create one. If there is a shopping cart in the database, then after a successful login they will be in the home page.

*********************************************
# Logout
In the home page, the user can log out of their account by clicking logout.

*********************************************
# CRUD service
- Create
- A shopping cart document contains the following attributes with an example:
  1) ownerID (admin1)
  2) magicPotion (1)
  3) invisibilityCloak (2)
  4) spellbookOfEnchantments (3)
  5) flyingBroomstick (4)
  6) crystalBall (5)

  ownerID is the user's login name. The user does not have to input it when creating a shopping cart.
  When creating a shopping cart document, the user must have at least one item otherwise, they wouldn't be able to create a document.
********************************************
# CRUD service
- Read
- There are two options to read and find items in our website.

1) In the checkout page, the user's whole shopping cart will be shown.

2) In the search page, the user can search whether they have a certain item in their shopping cart. For example, when they search magicPotion, it will show the number of magicPotion's they have in their cart.
********************************************
# CRUD service
- Update
- The user can update their cart information by typing out the item they want to update and quantity then click the update button. Once they click checkout, they will see that the amount has changed.

A shopping cart document contains the following attributes:
  1) magicPotion
  2) invisibilityCloak
  3) spellbookOfEnchantments
  4) flyingBroomstick
  5) crystalBall

These 5 attributes can be changed in the update page. However, the user will have to type the exact words to update otherwise it wouldn't work.
********************************************
# CRUD service
- Delete
- The user can delete their cart information in the checkout page.

*********************************************
# Restful
In this project, there are three HTTP request types, post, get, put and delete.
- Post 
	Post request is used for inserting a new document.
	Path URL: api/cart
	Test: curl -X POST -H "Content-Type: application/json" -d '{
	"magicPotion": 2,
	"invisibilityCloak": 1,
	"spellbookOfEnchantments": 3,
  	"flyingBroomstick": 1,
   	"crystalBall": 0
	}' http://localhost:8099/api/cart


- Get
	Get request is used to find the user's shopping cart.
	Path URL: api/cart/:userID
	Test: curl http://localhost:8099/api/cart/admin

- Put
	Put request is used for updating a existing shopping cart document.
	Path URL: api/cart/:userID
	Test:curl -X PUT -H "Content-Type: application/json" -d '{
    	"magicPotion": 3,
    	"invisibilityCloak": 2,
    	"spellbookOfEnchantments": 4,
    	"flyingBroomstick": 2,
   	"crystalBall": 1
	}' http://localhost:8099/api/cart/admin


- Delete
	Delete request is used for deletion of a shopping cart.
	Path URL: /api/cart/:userID
	Test: curl -X DELETE http://your-server-url/api/cart/admin


For all restful CRUD services, login should be done at first.


curl -X POST -H "Content-Type: application/json" --data '{"name": "Taro & Tea", "restaurangID":"00000004"}' http://localhost:8099/api/item/restaurantID/00000004

curl -X GET http://localhost:8099/api/item/restaurantID/00000002

curl -X DELETE http://localhost:8099/api/item/restaurantID/00000002
