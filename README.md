# homeworkFxPro
Portfolio to demonstrate my business and systems analyst skills for FxPro.
Some details of requirements were removed or changed due to NDA.

----------------------
### Table of Contents
[Sequence diagram (Mobile banking and core banking system example)](https://github.com/noyanSlamiya/homeworkFxPro/edit/main/README.md#sequence-diagram-in-resctricted-webapi-access)

[Frontend requirements 1 (Marketplace catalog transition map example)](https://github.com/noyanSlamiya/homeworkFxPro/edit/main/README.md#frontend-requirements-1-marketplace-catalog-transition-map-example)

[Frontend requirements 2 (Borrower application form requirements example)](https://github.com/noyanSlamiya/homeworkFxPro/edit/main/README.md#frontend-requirements-2-borrower-application-form-requirements-example)

[Integration with external systems (AccessTrade leadgenerator integration according to their API documentation)](https://github.com/noyanSlamiya/homeworkFxPro/edit/main/README.md#integration-with-external-systems-accesstrade-leadgenerator-integration-according-to-their-api-documentation)

-----------------------

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

### Creating CBS User sequence diagram
![image](https://github.com/noyanSlamiya/homeworkFxPro/assets/130692660/cac306de-0527-4281-a2f9-69ffd35d77d6)

### Processing a Request in WebAPI sequence diagram
![image](https://github.com/noyanSlamiya/homeworkFxPro/assets/130692660/5115faa7-3cdc-44a0-bdde-5d62d2d76cda)

### fetchRestrictedAccess() BPMN
![image](https://github.com/noyanSlamiya/homeworkFxPro/assets/130692660/a97fc292-fd62-4144-81b6-aa6a9ae88ff1)

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

## Event storming example

-------------------

## 

