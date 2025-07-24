## UML
```mermaid
classDiagram
    %% Feature 3: Basic Coffee model
    class Coffee {
      +String id
      +String name
      +String description
      +Number price
      +String imageUrl
    }

    %% Feature 4: Add Cart & Order
    class Item {
      +String coffeeId
      +Number quantity
    }
    class Cart {
      +String id
      +String userId
      +Array<Item> items
    }
    class Order {
      +String id
      +String userId
      +Array<Item> items
      +String status
      +Date createdAt
    }

    %% Feature 5: Add Auth (User & Role)
    class User {
      +String id
      +String username
      +String email
      +String firstName
      +String lastName
    }
    class Role {
      +String name
    }

    %% Relationships
    Coffee --* Item         : coffeeId
    Cart o-- Item           : items
    Order o-- Item          : items
    User "1" <-- "*" Cart   : userId
    User "1" <-- "*" Order  : userId
    User "*)" <-- "*" Role  : roles
```
## Component Tree Diagram
```mermaid
classDiagram
    App --|> HomePage
    App --|> MenuPage
    App --|> CartPage
    MenuPage --|> CoffeeService
    CoffeeService ..> CoffeeModelService
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
    Routes --|> MyOrders
    Routes --|> AdminOrders
```
## Component Tree Diagram
```mermaid
classDiagram
    Components --|> ProtectedRoute
    Components --|> PublicRoute
    Components --|> AdminRoute

    ProtectedRoute --> isAuthenticated
    PublicRoute --> isAuthenticated
    AdminRoute --> isAdmin

    ProtectedRoute --|> CartPage
    ProtectedRoute --|> MyOrders

    AdminRoute --|> AdminOrders

    PublicRoute --|> AuthModule
    AuthModule --|> AuthLogin
    AuthModule --|> AuthRegister
    AuthModule --|> AuthNav
