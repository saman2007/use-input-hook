
# useInput react custom hook
useInput is a custom hook that helps you validate your inputs very easier with giving you created functions.

## what is my purpose?
i had to create a lot of functions to validate just an input! and to validate a form that has 4 or 5 inputs, i had to crate a lot of functions that do almost the same as the other. so i told myself why dont you create a react custom hook to validate your inputs easier without writing functions that do the same thing? and i created this custom hook! an other purpose is that i really like to help other developer with creating tools. so i do my best to create useful tools to help the community even a little.

## what new things did i learn?
i learned that i always should think about making my works easier. because it helps me write more readable codes.
## how to use?
its really easy to use. lets create a simple email input with validation using this custom hook. this example shows you how to use this hook:
```javascript
import useInput from 'where this hook is'

//your component
function EmailInput() {
  //create a function that has an argument and return true or false
  //useInput always pass the current value to this function to validate the value
  const validate = (value) => /[^@ \t\r\n]+@[^@ \t\r\n]+\.[^@ \t\r\n]+/.test(value);

  //use the hook and destructure some properties
  //pass the validation function in the first argument
  //pass a boolean in the second argument that select input is require or not
  const {
    hasError,
    isFormValid,
    isTouched,
    onBlurHandler,
    value,
    onChangeHandler,
  } = useInput(validate, true);

  return <>
           //pass the returned onChange and onBluer handler to the onChange and onBlur event
           <input type="text" onChange={onChangeHandler} onBluer={onBlurHandler} />
           //display your error conditionally base on isFormValid, isTouched and hasError
           {!isFormValid && isTouched && hasError && <p>invalid entered value!</p>}
         </>
           //our email input is ready to use now :)
}
```

## whats next?
this is just a custom hook to make your validating forms easier. of course it can be easier than this. and im working on a component that make your validating easier than this. and you can join me to create this component.

## Authors
- [@saman2007](https://github.com/saman2007)
