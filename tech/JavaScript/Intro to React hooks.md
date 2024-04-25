#### Frequency 

Likely to use: (useState, useEffect, useContext, useRef, useReducer)
Not likely to use: (useMemo, useCallback, useLayoutEffect, useImperativeHandle, useDebugValue & useId)

#### useContext

```JavaScript, HTML 
import {useContext, createContext} from "react";


const UserContext = createContext([
{
	firstName: "Linna",
	lastName: "Li",
	suffix: 1,
	email: "example@email.com"
	},
	(obj) => obj
])

const LevelFive =() => {
	// pull out values from context when stored using createContext
	const [user, setUser] = useContext(UserContext)
}

const ContextComponentFive = () =>{

	return(
		<>
		<UserContext.Provider value={UserContext}>
		<h5> fifth level </h5>
		<LevelFive/>
		</UserContext.Provider>
		</>
	)
}


```

useContext is scoped to what is within the Context Provider
Can use useContext with useReducer to get most of what Redux gives you
You can make a context for different data objects but can also combine different data into one object

#### useRef

```javaScript
numRef = useRef(0)
// numRef is an object with only one key numRef.current
// useRef used if you need the most current state
// it's an object so that you can make sure you're able to change value but track the same object 
```

#### useReducer

Idea of store and redux is that you have a centralized placed where you store your state and you pass it an action that will update the state
A reducer function takes in a state and an action and then returns the new state
Reducer action is passed a new object that is assigned the new state and returned; does an equality check between object to be returned and current state that is to be changed before updating object to be returned and returning

useState and useReducer do the same things, useReducer is idempotent and testable; same state and action will yield the same result
Another tool is xState to prevent states from being in impossible states (being alive and dead at the same time in a video game)

#### useMemo

use for memoizing expensive functions; want to allow some other part of the component to change without running the expensive function on rerender
ie. color changes on the component while fibonacci calculator is being calculated
Don't rerun the expensive calculation as long as the input  value for the expensive function is not changing
Do not use this everywhere because it might cause state to not change when you're expect it to in non-obvious ways; only optimize when there is a problem with performance

#### useCallback

Prevent rerender when the new instances of the same function gets created; Refer and use the same function on rerenders so that new functions don't get created and ran
Need to use `memo()`  function for this to work

#### CodeSplitting

When you have VERY LARGE application, you don't want the users to wait for the application to load; you want to send them the most important things first and then load in the background as they interact with the application in an as needed basis

Need to have to split out at least 1000KB for it to make sense; don't start splitting when the app is small