
## Key TypeScript Concepts Used

Let me explain the key TypeScript concepts used in these conversions:

1. **Interfaces**
   - Created `GreetingProps` and `CounterState` interfaces to define the shape of our data
   - TypeScript interfaces provide compile-time checking of object shapes

2. **Type Annotations**
   - Added `React.FC<GreetingProps>` to the functional component
   - Used `Component<CounterProps, CounterState>` for the class component
   - Added `: void` return type to the increment method

3. **Generic Types**
   - `React.FC<T>` is a generic type that takes our props interface as a type parameter
   - `Component<P, S>` is a generic class that takes props and state interfaces

These changes make the code more robust by ensuring that:
- The `name` prop is always a string in the Greeting component
- The `count` state is always a number in the Counter component
- The components are used correctly throughout the application

<CodeProject id="typescript-conversion">

```tsx file="greeting.tsx"
import React from 'react';

// Define an interface for the component props
interface GreetingProps {
  name: string; // The name prop is a string
}

// Add the type annotation to the component using the interface
const Greeting: React.FC<GreetingProps> = ({ name }) => {
  return <div>Hello, {name}!</div>;
};

export default Greeting;
