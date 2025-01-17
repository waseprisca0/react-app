# react-app

Available Plugins
Two official plugins are supported for React development with Vite:

@vitejs/plugin-react: Uses Babel for Fast Refresh.
@vitejs/plugin-react-swc: Uses SWC for Fast Refresh.
Expanding ESLint Configuration
To enhance your ESLint setup for production applications, you can enable type-aware lint rules by following these steps:

Update parserOptions: Configure the parserOptions property to include your project's tsconfig files:

javascript
Copy
Edit
export default tseslint.config({
  languageOptions: {
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
});
Use Type-Checked ESLint Configurations: Replace tseslint.configs.recommended with:

tseslint.configs.recommendedTypeChecked for stricter type checking.
Optionally add ...tseslint.configs.stylisticTypeChecked for stylistic checks.
Install and Configure eslint-plugin-react: Install the plugin and update your ESLint configuration to include React-specific rules:

javascript
Copy
Edit
// eslint.config.js
import react from 'eslint-plugin-react';

export default tseslint.config({
  settings: { react: { version: '18.3' } }, // Set React version
  plugins: { react }, // Add the React plugin