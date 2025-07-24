
## Component Tree Diagram
```mermaid
classDiagram
    App --|> HomePage
    App --|> MenuPage
    App --|> CartPage
    MenuPage --|> CoffeeService
    CoffeeService ..> CoffeeModelService
```
