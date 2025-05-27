#Nike ERDiagram

erDiagram
    PRODUCT {
        int product_id PK
        string Nike
        string category
        string Adult
        float $100+
    }

    CUSTOMER {
        int customer_id PK
        string first_name
        string last_name
        string email
        string phone
    }

    SALE {
        int sale_id PK
        date sale_date
        int customer_id FK
        int product_id FK
        int quantity
        float total_price
    }

    INVENTORY {
        int inventory_id PK
        int product_id FK
        int quantity_in_stock
        string warehouse_location
    }

    CUSTOMER ||--o{ SALE : places
    PRODUCT ||--o{ SALE : includes
    PRODUCT ||--|| INVENTORY : stocked_in
