# Project Setup Documentation

## How to Create and Maintain a Professional Codebase in React and Next.js with Tailwind CSS v4

### Project Setup Steps

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

### Configure Tailwind CSS

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

13. Add the Tailwind CSS import globally inside your CSS file:
```css
@import "tailwindcss";
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

6. Documentation Links:
- Vite with Tailwind CSS: [Tailwind CSS Vite Installation Guide](https://tailwindcss.com/docs/installation/using-vite)
- Next.js with Tailwind CSS: [Tailwind CSS Next.js Installation Guide](https://tailwindcss.com/docs/installation/framework-guides/nextjs)

### Navigation
[Go to React Project Setup](#project-setup-steps)
[Go to Next.js Project Setup](#nextjs-project-setup)
