## Component Tree Diagram
```mermaid
classDiagram
    
    App --|> Navbar
    App --|> MainContent
    MainContent--|> HomePage
    MainContent --|> MenuPage
    MainContent --|> CartPage
    MainContent --|> MyOrders
