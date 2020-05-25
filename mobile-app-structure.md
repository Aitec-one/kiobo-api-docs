# User Flow

App has 4 main tabs:

- **Main Tab / Special Offers**
- **Catalog**
- **Place finder**
- **Profile**

as well as a Basket (on the right side of Navigation Bar) containing products selected by the user.

The user enters a phone number and confirms it at the entrance to the application. 
This is necessary to activate the loyalty program associated with the phone number.

In the course of using the application, the user also indicates his name, email and other personal data (optional), 
as well as the delivery address. Binds bank cards for payments.

During checkout, the user can choose delivery or pickup. 
Next, the user indicates the delivery address (its default delivery address), or the place where he will pick up his order.

Depending on the client’s settings, there may be payment to the courier or payment on the spot.

![User Flow!](User%20Flow%20Diagram.svg "User Flow Diagram")


# Initial Load

Upon authorization, the application receives an access token, which it stores in a keychain for further calls to the API.
When accessing the API, the access token is indicated in the request header as "Bearer: accessToken".

After logging in, the application loads all the necessary information: special offers, locations, product catalog, 
information about the user and his orders, etc.

The application can save the downloaded information, 
as well as download only the changed information using the versioning mechanism / etag.


![User Flow!](Kiobo.%20Mobile%20App%20Interaction.%20Init.svg "Sequence diagram")

# Order

After the initial download, the application checks for open orders and opens them; otherwise, a new order is created.

Each order change: adding a product to the cart, deleting a product, changing it — are sent to the server.


During checkout (in the cart screen), the user chooses the type of delivery: delivery or pickup.

![User Flow!](Kiobo.%20Mobile%20App%20Interaction.%20Order.svg "Sequence diagram")
