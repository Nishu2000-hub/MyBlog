## UML
```mermaid
classDiagram
    %% Core Coffee model (Feature 3)
    class Coffee {
      +id: String
      +name: String
      +description: String
      +price: Number
      +imageUrl: String
    }

    %% Cart & Order added (Feature 4)
    class Item {
      +coffeeId: String
      +quantity: Number
    }
    class Cart {
      +id: String
      +items: Item[]
    }
    class Order {
      +id: String
      +items: Item[]
      +status: String
      +createdAt: Date
    }

    %% Authentication & Roles added (Feature 5)
    class User {
      +id: String
      +username: String
      +email: String
      +firstName: String
      +lastName: String
    }
    class Role {
      +name: String
    }

    %% Relationships
    Cart "1" o-- "*" Item    : contains
    Order "1" o-- "*" Item   : contains
    Item "*" --> "1" Coffee  : references
    Cart "1" --> "1" User    : belongsTo
    Order "*" --> "1" User   : belongsTo
    User "*" -- "*" Role     : assigned

```
## Component Tree Diagram
```mermaid
classDiagram
    App --|> Components
    Components --|> Header
    Components --|> MenuList
    MenuList--|> MenuItem
    Components --|> Orderform
    Components --|>OrderSummary
```

## Component Tree Diagram
```mermaid
classDiagram
    BrowserRouter --|> Components
    Components --|> Navbar
    Components --|> Routes

    Routes --|> HomePage
    Routes --|> MenuPage
    Routes --|> CartPage
    Routes --|> 404-Not Found
```
## Component Tree Diagram
```mermaid
classDiagram
    Components --|> ProtectedRoute
    Components --|> PublicRoute


    ProtectedRoute --|> CartPage
    ProtectedRoute --|> MyOrders


    PublicRoute --|> AuthModule
    AuthModule --|> AuthLogin
    AuthModule --|> AuthRegister
    AuthModule --|> AuthNav
