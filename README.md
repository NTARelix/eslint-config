# NTARelix's ESLint Config
A set of opinionated ESLint (https://eslint.org) rules

## Usage

### Base Setup (or just JavaScript)
1. `npm install --save-dev @ntarelix/eslint-config`
2. Create a file named `.eslintrc.js` in your project
    ```diff
    +   module.exports = {
    +     root: true,
    +     extends: [
    +       '@ntarelix/eslint-config/base',
    +     ],
    +     rules: {
    +       // your rule overrides
    +     },
    +   }
    ```

### TypeScript Setup
Equivalent to adding TypeScript linting: https://github.com/typescript-eslint/typescript-eslint/blob/dac8845c6821d51cea5bafdc0be2e9a399cea68c/docs/getting-started/linting/README.md

1. Follow "Base Setup"
2. `npm install --save-dev @typescript-eslint/eslint-plugin @typescript-eslint/parser`
3. Modify `.eslintrc.js`
    ```diff
      module.exports = {
        root: true,
    +   parser: '@typescript-eslint/parser',
    +   plugins: [
    +     '@typescript-eslint',
    +   ],
        extends: [
          '@ntarelix/eslint-config/base',
    +     '@ntarelix/eslint-config/typescript',
        ],
        rules: {
          // your rule overrides
        },
      }
    ```

### TypeScript Setup with Type Information
Equivalent to adding TypeScript's type-aware linting: https://github.com/typescript-eslint/typescript-eslint/blob/dac8845c6821d51cea5bafdc0be2e9a399cea68c/docs/getting-started/linting/TYPED_LINTING.md

1. Follow "TypeScript Setup"
2. Modify `.eslintrc.js`
    ```diff
      module.exports = {
        root: true,
        parser: '@typescript-eslint/parser',
    +   parserOptions: {
    +     tsconfigRootDir: __dirname,
    +     project: ['./tsconfig.json'],
    +   },
        plugins: [
          '@typescript-eslint',
        ],
        extends: [
          '@ntarelix/eslint-config/base',
          '@ntarelix/eslint-config/typescript',
        ],
        rules: {
          // your rule overrides
        },
      }
    ```

### React Setup
1. Follow "TypeScript Setup"
2. `npm install --save-dev eslint-plugin-react eslint-plugin-react-hooks`
3. Modify `.eslintrc.js`
    ```diff
      module.exports = {
        root: true,
        parser: '@typescript-eslint/parser',
        plugins: [
          '@typescript-eslint',
    +     'react',
    +     'react-hooks',
        ],
        extends: [
          '@ntarelix/eslint-config/base',
          '@ntarelix/eslint-config/typescript',
    +     '@ntarelix/eslint-config/react',
        ],
        rules: {
          // your rule overrides
        },
      }
    ```
