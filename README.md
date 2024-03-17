# homeworkFxPro
Portfolio to demonstrate my business and systems analyst skills for FxPro.

The first example provides a high-level system description of the FxPro trading platform's IB portal through ERD and state diagrams, along with a brief introduction to potential Java classes and methods. There may be certain domain inconsistencies, however, I need a thorough analysis of the domain's business aspects to refine and enhance the accuracy of the model.

Other examples highlight key aspects of my requirements from previous projects, focusing on artifacts such as sequence diagrams, BPMN, and frontend transition maps. Some details couldn't be shared or were changed on purpose because of confidentiality agreements with companies I've worked for. But overall, the information still shows what I can do.

----------------------
### Table of Contents

[High-level system description of FxPro trading platform's IB portal](https://github.com/noyanSlamiya/homeworkFxPro?tab=readme-ov-file#high-level-description-of-fxpro-trading-platforms-ib-portal)

* [Overview of IB Portal](https://github.com/noyanSlamiya/homeworkFxPro?tab=readme-ov-file#overview-of-ib-portal)
* [State diagram of IB Portal](https://github.com/noyanSlamiya/homeworkFxPro?tab=readme-ov-file#state-diagram-of-ib-portal)
* [ER diagram of IB Portal, coupled with client (trader) entities and objects](https://github.com/noyanSlamiya/homeworkFxPro?tab=readme-ov-file#er-diagram-of-ib-portal-coupled-with-client-trader-entities-and-objects)
* [Examples of IB Portal Java classes and methods](https://github.com/noyanSlamiya/homeworkFxPro?tab=readme-ov-file#examples-of-ib-portal-java-classes-and-methods)

[Sequence diagram (Mobile banking and core banking system example)](https://github.com/noyanSlamiya/homeworkFxPro?tab=readme-ov-file#sequence-diagram-mobile-banking-and-core-banking-system-example)

* [Overview](https://github.com/noyanSlamiya/homeworkFxPro?tab=readme-ov-file#overview)
* [Glossary](https://github.com/noyanSlamiya/homeworkFxPro?tab=readme-ov-file#glossary)
* [Creating CBS User (sequence diagram)](https://github.com/noyanSlamiya/homeworkFxPro?tab=readme-ov-file#creating-cbs-user-sequence-diagram)
* [Processing a Request in WebAPI (sequence diagram)](https://github.com/noyanSlamiya/homeworkFxPro?tab=readme-ov-file#processing-a-request-in-webapi-sequence-diagram)
* [fetchRestrictedAccess() (BPMN)](https://github.com/noyanSlamiya/homeworkFxPro?tab=readme-ov-file#fetchrestrictedaccess-bpmn)

[Frontend requirements 1 (Marketplace catalog transition map example)](https://github.com/noyanSlamiya/homeworkFxPro?tab=readme-ov-file#frontend-requirements-1-marketplace-catalog-transition-map-example)

[Frontend requirements 2 (Borrower application form requirements example)](https://github.com/noyanSlamiya/homeworkFxPro?tab=readme-ov-file#frontend-requirements-2-borrower-application-form-requirements-example)

[Integration with external systems (AccessTrade leadgenerator integration according to their API documentation)](https://github.com/noyanSlamiya/homeworkFxPro?tab=readme-ov-file#integration-with-external-systems-accesstrade-leadgenerator-integration-according-to-their-api-documentation)

-----------------------

## High-level description of FxPro trading platform's IB portal

### Overview of IB Portal
The FxPro IB Portal is made for Introducing Brokers and has a bunch of important parts that make it easier to handle client referrals, keep track of commissions, and use financial products. Here's a simple overview of the main parts in the FxPro IB Portal:

1. **_Introducing Broker Profiles_**: This is the main part of the portal. It has all the important details about each broker like personal info, contact details, and if they meet certain rules.
2. **_Client Management_**: This part lets brokers look after their clients, including their registration info, how they trade, and their account status. It's like a big dashboard for watching over client activities and needs.
3. **_Commission Structures_**: This shows the different ways brokers can earn commissions. It keeps track of commissions as they're earned, payment history, and detailed reports based on what clients do and the volumes they trade.
4. **_Marketing Tools_**: This includes stuff for promotion, link generators, and other resources to help brokers get and keep clients. It often has banners you can change, stuff to learn from, and tools to see how well campaigns are doing.
5. **_Performance Analytics_**: This gives detailed reports and tools to see into how clients are gotten, how much they trade, earnings from commissions, and other important performance info. It helps brokers make their strategies better and work more efficiently.
6. **_Training and Support_**: This has learning resources, guides, and help materials to assist brokers in getting to know FxPro's products, how the platform works, and tips for growing their business.
7. **_Account and Payment Settings_**: This lets brokers handle their account details, choose how they want to get paid, and take out commissions. It offers tools for managing money and makes sure everything runs smoothly in the portal.

All these parts are put together to give Introducing Brokers what they need to manage client referrals well, watch their performance, and get the most out of their commissions, all while getting good support from FxPro.

### State diagram of IB Portal
![IBPortalStateDiagram-2024-03-17-190016](https://github.com/noyanSlamiya/homeworkFxPro/assets/130692660/1dd8c8c8-353a-49d3-b929-a16930f8cf4f)

### ER diagram of IB Portal, coupled with client (trader) entities and objects
![Untitled diagram-2024-03-17-202159](https://github.com/noyanSlamiya/homeworkFxPro/assets/130692660/583d4ae0-832a-4300-8d6b-b64d29d62ffb)

### Examples of IB Portal Java classes and methods

**IBroker Entity**
```java
import java.util.List;
import java.util.UUID;

public class IBroker {
    private UUID brokerID;
    private String name;
    private String email;
    private List<Client> clients;
    private List<ProductsServices> offeredProductsServices;
    private List<IBAccount> ibAccounts;

    // Method to add a client to the broker's list
    public void addClient(Client client) {
        this.clients.add(client);
    }

    // Other constructors, getters, setters
}
```

**Client Entity**

```java
import java.util.List;
import java.util.UUID;

public class Client {
    private UUID clientID;
    private String name;
    private String email;
    private UUID brokerID;
    private List<Trade> trades;
    private List<ClientAccount> clientAccounts;
    private List<ProductsServices> usedProductsServices;

    // Method to add a trade to the client's list
    public void addTrade(Trade trade) {
        this.trades.add(trade);
    }

    // Other constructors, getters, setters
}
```

**ClientAccount Entity**

```java
import java.util.UUID;

public class ClientAccount {
    private UUID accountID;
    private UUID clientID;
    private String type;
    private float balance;

    // Method to update the account balance
    public void updateBalance(float amount) {
        this.balance += amount; // Assuming positive for deposits, negative for withdrawals
    }
    
    // Other constructors, getters, and setters
}
```

**IBAccount Entity**

```java
import java.util.UUID;

public class IBAccount {
    private UUID ibAccountID;
    private UUID brokerID;
    private String type;
    private float balance;

    // Method to process commission payments
    public void processCommissionPayment(float amount) {
        // Assuming amount is positive for incoming payments
        this.balance += amount;
    }
    
    // Other constructors, getters, and setters

}
```

-------------------------

## Sequence diagram (Mobile banking and core banking system example)

### Overview
The WebAPI access service acts as a mediator between the middleware and the Core Banking System (CBS) within the context of secure access to the CBS through WebAPI methods, which require the presence of an internet banking (IB) user and his access keys (tokens).
Thus, a client's request first processed by middleware, which checks authorization in the WebAPI access service to send request to the CBS's WebAPI.

### Glossary
| entity or object | Definition |
| --- | --- |
| accessToken | client access token in the bank application that issues Client's ecosystem ID in  |
| refreshToken | client access refresh token in bank application that issues Clients's ecosystem ID |
| sub | unique client identifier in ecosystem, synonym of userId |
| userId | unique client identifier in ecosystem, synonym of sub |
| customerId | unique client identifier in core banking system (CBS) |
| restrictedAccessToken | access token to CBS (WebAPI) |
| restrictedRefreshToken | refresh token to CBS (WebAPI) |
| restrictedTokenIssuedAt | refresh token issued date and time |
| restrictedTokenExpiredAt | refresh token expired date and time |
| restrictedUsername | customer name in CBS |
| restrictedPassword | customer password in CBS |

### Creating CBS User (sequence diagram)
![image](https://github.com/noyanSlamiya/homeworkFxPro/assets/130692660/cac306de-0527-4281-a2f9-69ffd35d77d6)

### Processing a Request in WebAPI (sequence diagram)
![image](https://github.com/noyanSlamiya/homeworkFxPro/assets/130692660/5115faa7-3cdc-44a0-bdde-5d62d2d76cda)

### fetchRestrictedAccess() (BPMN)
![fetchAccess](https://github.com/noyanSlamiya/homeworkFxPro/assets/130692660/c7e64663-5fdf-4267-a499-6304ec42ffc7)


---------------------

## Frontend requirements 1 (Marketplace catalog transition map example)
<img width="10288" alt="marketplace_videostreaming" src="https://github.com/noyanSlamiya/homeworkFxPro/assets/130692660/33f90ddc-2b29-48c8-ba49-cf5ebf1873fd">

----------------------

## Frontend requirements 2 (Borrower application form requirements example)
<img width="1300" alt="Screenshot 2024-03-17 at 18 45 00" src="https://github.com/noyanSlamiya/homeworkFxPro/assets/130692660/538e848c-5ce0-4406-b93b-d6e44f4eb4c7">
<img width="1367" alt="Screenshot 2024-03-17 at 18 46 17" src="https://github.com/noyanSlamiya/homeworkFxPro/assets/130692660/382858f8-6968-493d-83e3-140c60b7c557">
<img width="1367" alt="Screenshot 2024-03-17 at 18 50 48" src="https://github.com/noyanSlamiya/homeworkFxPro/assets/130692660/429a2c29-654b-494f-96d6-a99aee87af45">
<img width="13088" alt="application form-min" src="https://github.com/noyanSlamiya/homeworkFxPro/assets/130692660/87a74258-33b2-42b3-84bb-59483d7c90a8">

---------------------

## Integration with external systems (AccessTrade leadgenerator integration according to their API documentation)
![AccessTrade lead generator](https://github.com/noyanSlamiya/homeworkFxPro/assets/130692660/bcbe033b-6ef2-494e-b7bc-f41a144d7425)
<img width="865" alt="Screenshot 2024-03-17 at 19 17 58" src="https://github.com/noyanSlamiya/homeworkFxPro/assets/130692660/910bdf11-d9ee-4204-90d5-c2023f249d1e">

-------------------
