# Project Setup Documentation For React.js & Next.js

## How to Create and Maintain a Professional Codebase in React and Next.js with Tailwind CSS v4 + TypeScript

### React.js Project Setup Steps 

1. Create the project using Vite:
```bash
npm create vite@latest
```
2. Enter your project name and press Enter.
3. Select your preferred framework (React).
4. Select the variant (TypeScript or JavaScript).
5. Navigate to your project directory:
```bash
cd your-project-name
```
6. Install project dependencies:
```bash
npm install
```

### Install Tailwind CSS

7. Install Tailwind CSS and its peer dependencies:
```bash
npm install -D tailwindcss postcss autoprefixer
```
8. Initialize Tailwind CSS configuration:
```bash
npx tailwindcss init -p
```

### Configure Tailwind CSS (Old way before V4)

9. Inside `tailwind.config.js` or `tailwind.config.ts`, set up the content paths:
```js
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}"
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

### Add Tailwind CSS to Your Project

10. Inside `src/index.css`, add the Tailwind CSS directives:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### Tailwind CSS v4 Configuration (New Way)

11. Install the Vite plugin for Tailwind CSS:
```bash
npm install -D @tailwindcss/vite
```

12. Update your `vite.config.ts` or `vite.config.js` file:
```js
import { defineConfig } from 'vite'
import tailwindcss from '@tailwindcss/vite'

export default defineConfig({
  plugins: [
    tailwindcss(),
  ],
})
```

13. Add the Tailwind CSS import globally inside your index.css file:
```css
@import "tailwindcss";
```

### React Routing Setup

1. Inside the `layouts` folder, create a `MainLayout` (You can use your preferable name) component that renders its `children` prop.

2. In the `routes` folder, create a `routes.tsx` or `routes.jsx` file and paste the following code:
```tsx
import { createBrowserRouter } from "react-router-dom";
import MainLayout from "../layouts/MainLayout";
import Home from "../pages/Home";
import NotFound from "../pages/NotFound";

export const router = createBrowserRouter([
  {
    path: "/",
    element: <MainLayout />,
    errorElement: <NotFound />,
    children: [
      {
        path: "/",
        element: <Home />,
      },
    ],
  },

  // Add more routes here if needed
]);
```

3. In `main.tsx` or `main.jsx`, import the routes and use `RouterProvider`:
```tsx
import React from 'react'
import ReactDOM from 'react-dom/client'
import './index.css'
import { RouterProvider } from 'react-router-dom'
import { router } from './routes/routes'

ReactDOM.createRoot(document.getElementById('root')!).render(
  <React.StrictMode>
    <RouterProvider router={router} />
  </React.StrictMode>
)
```

### Start the Project

14. Run the project:
```bash
npm run dev
```

### Project Structure
```
├─ public
├─ src
│  ├─ assets
│  ├─ components
│  ├─ pages
│  ├─ styles
│  └─ main.tsx
├─ index.html
└─ package.json
```

### Folder Explanation
- `src/components`: Reusable components.
- `src/pages`: Page components.
- `src/styles`: Global styles.
- `public`: Static assets.

### Best Practices
- Use functional components.
- Organize components into folders.
- Use TypeScript for type safety.
- Maintain consistent folder structure.
- Follow DRY (Don't Repeat Yourself) principle.
- Write clean, reusable code.

### Next.js Project Setup

1. Create the project using Next.js:
```bash
npx create-next-app@latest
```
2. Answer the prompts:
   - What is your project named? `my-app`
   - Would you like to use TypeScript? `No / Yes`
   - Would you like to use ESLint? `No / Yes`
   - Would you like to use Tailwind CSS? `No / Yes`
   - Would you like your code inside a `src/` directory? `No / Yes`
   - Would you like to use App Router? (recommended) `No / Yes`
   - Would you like to use Turbopack for `next dev`? `No / Yes`
   - Would you like to customize the import alias (`@/*` by default)? `No / Yes`
   - What import alias would you like configured? `@/*`

3. Install Tailwind CSS:
```bash
npm install -D tailwindcss postcss autoprefixer
```

4. Create `postcss.config.mjs` with the following content:
```js
const config = {
  plugins: {
    "@tailwindcss/postcss": {},
  },
};
export default config;
```

5. Import Tailwind CSS globally:
```css
@import "tailwindcss";
```
6. Run the project:
```bash
npm run dev
```

7. Documentation Links:
- Vite with Tailwind CSS: [Tailwind CSS Vite Installation Guide](https://tailwindcss.com/docs/installation/using-vite)
- Next.js with Tailwind CSS: [Tailwind CSS Next.js Installation Guide](https://tailwindcss.com/docs/installation/framework-guides/nextjs)

### Deploy Project on Vercel

1. Create `vercel.json` file in the root of your project.
2. Paste the following code inside the file:
```json
{
  "rewrites": [{ "source": "/(.*)", "destination": "/" }]
}
```

### Essential VS Code Extensions
- Auto Close Tag
- Auto Import
- Auto Rename Tag
- Bracket Pair Colorizer
- React Snippets
- Prettier
- React Extension Pack
- React Code Snippets
- Tailwind CSS IntelliSense
- Code Spell Checker
- Console Ninja
- JavaScript (ES6) Code Snippets
- Material Icon Theme

### Navigation  
[Go to React Project Setup](#project-setup-steps)  
[Go to Next.js Project Setup](#nextjs-project-setup)
