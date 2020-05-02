# React Hooks

## useState

> state + setState() == useState()

`useState` hook is the replacement of the `state` and `setState` in the class component.

```javascript
const [state, setState] = useState({
 selectedCharacter: 1,
 side: 'light',
 destroyed: false
}); 
```

In the above code we can simply passed the initial state to the useStaet hooks, useState hook return an array which has 2 things. First is the current state of the component, the second is the method used to update the state.

If we update the state using the method returned by useState then the whole state will be replaced by the state returned by the method. Lets an example, if the above is being updated as below,

```javascript
 const sideHandler = side => {
    setState({ side: side });
  };
```
then the whole state is being replaced and our new state will be as 

```
{
  side: dark
}
```
we will loose our all the other properties, **so the best practice during setState method returned by the useState is first destructure the previous state and then update it with new state as below** :

```javascript
 const sideHandler = side => {
    setState( {
    ....state,
     side: side
     });
  };
````  

## useEffect

> componentDidMount + componentDidUpdate + componentWillUnmount == useEffect()

`useEffect` hooks has been created to handle the side effects in the component. For example : http request.

`useEffect(() => {})` usEffect hook take a function, which will be executed only after the component has been changed.




`useEffect((() => {}),[]) == componentDidMount` when we pass the empty arrays as second argument then the useEffect will be excuted only once after the component has been and not on every component change.
























