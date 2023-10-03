# DISHP specification 

## Requirements
---
- Requesting data from a device 
- Getting the data from a device 
- Its all about asking and answering 
  
## Transaction kind
- ASK - Declares a request 
- ANS - Declares a response 
- <---> - Separated by three dashes 
  
## Header
- For: Specifies the kind of method that is asked/responded to 
  - action - Executes some kind of function
  - transfer - A transfer of requested data
- Ident: Identifies the request and response 
- State: Says if its the actual send transaction or the information response 
  - Init - Represents the initial request 
  - Info - Info from other component about the progress state 
- Code: The state of the request 
   - 100 - Declares a successful transaction
   - 200 - Declares a failed transaction 
- <---> - Separated by three dashes

## Body 
- JSON object 
- JSON array 
- <---> - Ends with three dashes 

## Building blocks 
- Transaction kind
- Header 
- Body 

## Examples
### Action
```
ASK
---
For: action 
Ident: e888a277-37b7-4c03-b7e6-df0043d7394c
State: Init
---
{
    
}
---
```

```
ANS
---
For: action 
Ident: e888a277-37b7-4c03-b7e6-df0043d7394c
State: Info 
Code: 100
---
{

}
---
```

### Transfer
```
ASK
---
For: transfer
Ident: ac4217c2-636d-499c-a7d8-8494ac68a9c7
State: Init 
---
{

}
---
```

```
ANS
---
For: transfer
Ident: ac4217c2-636d-499c-a7d8-8494ac68a9c7
State: Info
Code: 100
---
{

}
---
```
