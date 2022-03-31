is a state-management-system for cross component or app-wide state

redux is a flux-like state librari  <==============

## When do you want to use Redux

* You have many context states that you need to use cross many components, is a good choice because it makes the code easier to mantain rather than "React Context"
* If you need high frecuency updates is a good choice "Redux"

If you have low frecuency changes and fewer states to share between components you can use "react context".

## Redux functionality

It has a central strore for the state across the application. We can use the central store inside our components, our components, has to subscribe to our data store. Is important to appoint that components never change directly the data in the central store. To manipulate the date we have functions that are named as  "reducer functions". 

As we know the components dispatch actions, so those actions trigger the "reducer functions" of our "redux" then the function changes the state. And all the components that are subscribe are notified. 


## about reducer function

this function should:

* Be a pure function: for the same inputs always return the same response
* 
