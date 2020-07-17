## elintrc
- 1、npm init -y
- 2、git init 
- 3、npm install eslint --save-dev、
- 4、npm install standard --save-dev
- 5、touch .eslintrc.js
- 6、
  ```
  module.exports = {
    env: {
      browser: true,
      commonjs: true,
      es2020: true
    },
    extends: [
      'standard'
    ],
    parserOptions: {
      ecmaVersion: 11
    },
    rules: {
    }
  }

  ```
- 7、touch .gitignore
- 8、node_modules