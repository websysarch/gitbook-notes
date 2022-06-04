# Component's Architecture



### Layers

1. User Interface (UI) / Service Interface (APIs)
2. Business Logic (BL)
3. Data Access Layer (DAL)

#### Code Flow

* One layer could call only the next layer.
* A layer can not call its upper layer.

Valid Flow

UI -> BL -> DAL

In correct examples:

* Upward flow: DAL -> BL, BL -> UI / SI
* Skip level calls: UI -> DAL

#### Loose Coupling

