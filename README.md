             My first React App

Available Plugins
Two official plugins are supported for React development with Vite:

1. @vitejs/plugin-react: Uses Babel for Fast Refresh.
2. @vitejs/plugin-react-swc: Uses SWC for Fast Refresh.

        Expanding ESLint Configuration
To enhance your ESLint setup for production applications, you can enable type-aware lint rules by following these steps:

1. Update parserOptions: Configure the parserOptions property to include your project's tsconfig files:
       export default tseslint.config({
  languageOptions: {
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
});

2. Use Type-Checked ESLint Configurations: Replace tseslint.configs.recommended with:

     >tseslint.configs.recommendedTypeChecked for stricter type checking.
     >Optionally add ...tseslint.configs.stylisticTypeChecked for stylistic checks.
   
3. Install and Configure eslint-plugin-react: Install the plugin and update your ESLint configuration to include React-specific rules:
   // eslint.config.js
import react from 'eslint-plugin-react';

export default tseslint.config({
  settings: { react: { version: '18.3' } }, // Set React version
  plugins: { react }, // Add the React plugin
