# What is use case for using debouncing?

Let's say, you have a text input search bar, where user can search for products.  
In traditional way, as soon as user enters a character, we need to call an API to get the related products and display on the UI.  
The CONS behind this, is that it is very inefficient on UI as well as server side.  
A better way would be to limit / or delay the number of API calls as the user is typing.  

# What is debouncing?

Debouncing is a concept of delaying the API call, with the help of a timer. Timer is used to decide when to call a function.  
As soon as user types in the search bar, the timer of 't' milliseconds is started.  
Now as the timer is running, if there is another letter typed by the user, the timer is re-started.  
As soon as the timer runs out, the function is called.  

# Example

Time: 0ms -- User types: P.  
Timer is set for 500ms.  
Time: 150ms -- User types: A.  
Timer is re-set for 500ms.  
Time: 250ms -- User types: M.  
Timer is re-set for 500ms.  
No action from user till 500ms.  
Function is called.  

This is how the debounce function will operate.  

Given a function fn, and a time 't' seconds, write a debounced function.  
Debounced function will return a function which will call the function in debounced manner using 't' seconds.  

const deboucedFunction = debounce(fn, t);  
debouncedFunction();  