# CRA's configuration for Prettier and EsLint

- Eslint config :

  > `npx eslint --init`

  - **How would you like to use ESLint?**  
    _To check syntax, find problems and enforce code style_
  - **What type of modules does your project use?**  
    _Javascript module_
  - **Which framework does your project use?**  
    _React_
  - **Does your project use TypeScript?**  
    _No_
  - **Where does your code run?**  
    _Browser_
  - **How would you like to define a style for your project?**  
    _Use a popular style guide_
  - **Which style guide do you want to follow?**  
    _Airbnb_
  - **What format do you want your config file to be in?**  
    _JSON_

---

- Prettier config :
  > `npm install --save-dev prettier eslint-config-prettier eslint-plugin-prettier`

---

- Create files .eslintignore .prettierignore in project root to ignore build and modules :
  > ` build`  
  > `node_modules`

---

- Update eslint config in .eslintrc (many rules come from Oclock Yo template (spé react)) :

  ```
  {
  "env": {

  "browser": true,
  "es2021": true

  },
  "extends": ["react-app", "airbnb", "prettier"],
  "parserOptions": {
  "ecmaFeatures": {
  "jsx": true
  },
  "ecmaVersion": 13,
  "sourceType": "module"
  },
  "plugins": ["react", "prettier"],
  "rules": {
  "prettier/prettier": [
  "error",
  {
  "singleQuote": true
  }
  ],
  "brace-style": ["error", "stroustrup"],
  "no-param-reassign": [
  "error",
  {
  "props": false
  }
  ],
  "no-mixed-operators": [
  "error",
  {
  "allowSamePrecedence": true
  }
  ],
  "jsx-a11y/no-static-element-interactions": "off",
  "jsx-a11y/href-no-hash": "off",
  "jsx-a11y/anchor-is-valid": "off",
  "jsx-a11y/mouse-events-have-key-events": "off",
  "jsx-a11y/click-events-have-key-events": "off",
  "jsx-a11y/no-noninteractive-element-interactions": "off",
  "react/jsx-filename-extension": "off",
  "react/forbid-prop-types": "off",
  "react/no-access-state-in-setstate": "warn",
  "react/jsx-one-expression-per-line": "off",
  "react/destructuring-assignment": "warn",
  "react/no-unescaped-entities": "off",
  "react/jsx-props-no-spreading": "off",
  "react/state-in-constructor": "off",
  "func-names": "off",
  "object-shorthand": "off"
  }
  }

  ```

  - We can specify a severity for each Eslint rules :
  - 0 or 'off' : rule is disabled
  - 1 or 'warn' : rule violation causes a warn
  - 2 or 'error' : rule violation causes an error with exit code 1

---

- Update prettier config in .prettierrc file :

  ```
  {
  "trailingComma": "es5",
  "tabWidth": 2,
  "singleQuote": true
  }

  ```

---

- In VSC, update the settings.json to autoformat on save or other options :

  ```
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true
  },
  "[javascript]": {
      "editor.formatOnSave": false
  },
  "eslint.codeAction.showDocumentation": {
      "enable": true
  },
  "eslint.alwaysShowStatus": true,
  "prettier.disableLanguages": [
      "js"
  ]
  ```
