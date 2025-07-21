# Data dictionary of assignment_data.json
This dictionary will discuss the most relevant objects of the nested JSON data. The data in itself represents transactions of Point Of Sales. Each transaction can contain several items as well as other metadata regarding time of the transaction, discounts, loyalty card, etc.

## Attributes
The attributes may vary depending on the transaction. In this point, the main components will be described. However, we rely on your Data Engineering skills to make sense of the data as well.

**General metadata:**
- Version: data schema version
- Operation: -
- Source: object containing metadata regarding the dataset name, the operating company that it belongs two and the department who owns it.
- Reference: This should match the TransactionID

**Transactions:**
Indicated by the "after" key.
- StoreID: Unique identifier of the store (POS)
- WorkstationID: Id of the workstation within the store where the transaction is being processed
- StartDateTimestamp: Start timestamp of the transaction
- EndDateTimestamp: End timestamp of the transaction
- TenderDateTimestamp: Timestamp of the payment
- TransactionNumber: -
- OperatorID: Unique identifier of the operator
- ExternalSalesChannel: (not always present) indicates an external sales channel
- ExternalTransactionID: (not always present) links to an external sales channel
- LineItem: Object that may contain different SequenceNumbers concerning different objects and its metadata from the transaction
    - LoyaltyCard: metadata referring to the LoyaltyCard of the customer associated with the transaction
    - SalesItem: metadata regarding an item in the transaction
    - Discount: metadata regarding the discount within the transaction
    - Payment: metadata regarding the payment
    - VAT: metadata regarding the VAT of the transaction
    - Total: metadata regarding the total amount of the transaction
    - ...
