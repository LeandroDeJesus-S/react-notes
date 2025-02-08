[ESLint doc](https://eslint.org/docs/latest/use/getting-started)
```sh
npm install eslint --save-dev
npx eslint --init

# react
npm install eslint-plugin-react eslint-plugin-react-hooks --save-dev

# prettier
npm install eslint prettier eslint-plugin-prettier eslint-config-prettier --save-dev


# com ts
npm install @typescript-eslint/parser @typescript-eslint/eslint-plugin --save-dev

npm install @typescript-eslint/parser @typescript-eslint/eslint-plugin --save-dev

```

```mjs
import globals from 'globals';
import pluginJs from '@eslint/js';
import pluginReact from 'eslint-plugin-react';
import reactHooks from 'eslint-plugin-react-hooks';
import eslintPluginPrettier from 'eslint-plugin-prettier';

/** @type {import('eslint').Linter.Config[]} */
export default [
    {
        files: ['**/*.{js,mjs,cjs,jsx}']
    },
    pluginJs.configs.recommended,
    pluginReact.configs.flat.recommended,
    pluginReact.configs.flat['jsx-runtime'],
    {
        languageOptions: {
            globals: globals.browser,
            parserOptions: {
                ecmaFeatures: {
                    jsx: true
                }
            }
        },
        settings: {
            react: {
                version: 'detect'
            }
        },
        plugins: {
            pluginReact,
            'react-hooks': reactHooks,
            prettier: eslintPluginPrettier
        },
        rules: {
            'react/react-in-jsx-scope': 'off',
            'react-hooks/rules-of-hooks': 'error',
            'react-hooks/exhaustive-deps': 'warn',
            'prettier/prettier': 'error'
        }
    }
];
```