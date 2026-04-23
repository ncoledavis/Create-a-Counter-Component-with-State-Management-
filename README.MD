# React Counter

> A simple React project that demonstrates how `useState` works, how React batches updates, and why functional state updates matter.

---

## Overview
This is a simple React based counter that is meant to teach how the increment system works in react and how to plan your code returns and buttons not to miss certain entries or cause conflicting issues.
YouTube Link: https://youtu.be/WUBy9ERBgbs
---

## Buttons

### Increment
** What it does:** Increases the count by **1 immediately**.

** How it works:**
```jsx
setCount(count + 1)
```
React updates the current state value by one.

---

###  Increment After Delay
** What it does:** Waits **2 seconds**, then increases the count by **1**.

** How it works:**
```jsx
setTimeout(() => {
  setCount(prevCount => prevCount + 1)
}, 2000)
```
The updater function ensures the latest value is used after the delay.

---

### Increment Twice
** What it does:** Attempts to increase the count by **2**, but usually only increases by **1**.

** Why this happens:**
```jsx
setCount(count + 1)
setCount(count + 1)
```
Both updates use the same original state value before React re-renders.
---

### Correct Increment Twice
** What it does:** Correctly increases the count by **2**.

** Why it works:**
```jsx
setCount(prevCount => prevCount + 1)
setCount(prevCount => prevCount + 1)
```
Each update receives the newest state value.

** Example:**
- First update → `0 → 1`
- Second update → `1 → 2`

** Final Result:** Count increases by **2**.

##  Run the Project
```bash
npm install
npm run dev
```

---

## Built With
- React
- JavaScript (JSX)
- Vite

# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Oxc](https://oxc.rs)
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/)

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.
