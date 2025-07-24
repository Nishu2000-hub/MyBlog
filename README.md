
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
