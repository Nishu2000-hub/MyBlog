
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
    Components <|-- ProtectedRoute
    Components <|-- PublicRoute
    Components <|-- AdminRoute

    ProtectedRoute --> isAuthenticated
    PublicRoute --> isAuthenticated
    AdminRoute --> isAdmin

    ProtectedRoute <|-- CartPage
    ProtectedRoute <|-- MyOrders

    AdminRoute <|-- AdminOrders

    PublicRoute <|-- AuthModule
    AuthModule <|-- AuthLogin
    AuthModule <|-- AuthRegister
    AuthModule <|-- AuthNav
