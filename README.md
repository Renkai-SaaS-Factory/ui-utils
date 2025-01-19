# UI Utils Package

A simple and reusable utility library for modern JavaScript and TypeScript projects. This package includes functions like `cn` to merge Tailwind CSS classes and handle conditional styling easily.

---

## Installation

### Step 1: Install the Package

To get started, install the `ui-utils` package using npm or yarn:

```bash
# Using npm
npm install ui-utils

# Using yarn
yarn add ui-utils
```

### Step 2: Install Peer Dependencies

This package depends on `clsx` and `tailwind-merge`. Ensure they are installed:

```bash
npm install clsx tailwind-merge
```

---

## Usage

### Importing Functions

The `ui-utils` package provides several reusable utility functions. Here's an example of how to use the `cn` function:

```typescript
import { cn } from "ui-utils";

const buttonClass = cn(
  "px-4 py-2 font-bold rounded",
  isPrimary && "bg-blue-500 text-white",
  isDisabled && "opacity-50 cursor-not-allowed"
);

console.log(buttonClass);
// Output: "px-4 py-2 font-bold rounded bg-blue-500 text-white"
// or "px-4 py-2 font-bold rounded opacity-50 cursor-not-allowed"
```

---

## API Reference

### `cn`

Merges Tailwind CSS classes and conditionally applies them.

#### Parameters

- `inputs: ClassValue[]`: A list of classes, conditions, or arrays to merge.

#### Returns

- `string`: A merged string of valid Tailwind CSS classes.

#### Example

```typescript
const alertClass = cn(
  "p-4 border rounded",
  type === "success" && "bg-green-500 text-white",
  type === "error" && "bg-red-500 text-white"
);
```

---

## Examples

### Button Component

Create a simple button component using the `cn` function for conditional styling:

```tsx
import React from "react";
import { cn } from "ui-utils";

interface ButtonProps {
  label: string;
  isPrimary?: boolean;
  isDisabled?: boolean;
}

const Button: React.FC<ButtonProps> = ({ label, isPrimary, isDisabled }) => {
  const buttonClass = cn(
    "px-4 py-2 font-bold rounded",
    isPrimary && "bg-blue-500 text-white",
    isDisabled && "opacity-50 cursor-not-allowed"
  );

  return (
    <button className={buttonClass} disabled={isDisabled}>
      {label}
    </button>
  );
};

export default Button;
```

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.
