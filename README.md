## UML
```mermaid
classDiagram
    %% Feature 3: Core Domain (Component Architecture)
    class Coffee {
      +id: string
      +name: string
      +description: string
      +price: number
      +imageUrl: string
    }
    class Review {
      +id: string
      +rating: number
      +text: string
    }
    Coffee "1" o-- "*" Review : has reviews

    %% Feature 4: Cart Functionality (Routing & Parsing)
    class Cart {
      +id: string
      +user: User
      +items: CartItem[]
    }
    class CartItem {
      +coffeeId: string
      +quantity: number
    }
    Cart "1" o-- "*" CartItem : contains

    %% Feature 5: Orders & Authentication
    class Order {
      +id: string
      +user: User
      +items: OrderItem[]
      +status: string
    }
    class OrderItem {
      +coffeeId: string
      +quantity: number
    }
    Order "1" o-- "*" OrderItem : contains

    %% User & Roles (Auth)
    class User {
      +username: string
      +email: string
      +sessionToken: string
    }
    class Role {
      +name: string
    }
    User "1" <-- "1" Cart
    User "1" <-- "1" Order
    User "1" --> "*" Role : has roles
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
