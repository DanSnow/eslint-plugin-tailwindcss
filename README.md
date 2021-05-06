# eslint-plugin-tailwindcss

![npm (scoped)](https://img.shields.io/npm/v/eslint-plugin-tailwindcss?style=for-the-badge) ![npm bundle size (scoped)](https://img.shields.io/npm/l/eslint-plugin-tailwindcss?style=for-the-badge)

![eslint-plugin-tailwindcss logo](https://user-images.githubusercontent.com/704026/117105634-bd661300-ad7e-11eb-9cf1-a05ba130da34.png)

Rules enforcing best practices and consistency using [Tailwind CSS](https://tailwindcss.com/) v2.1.1

> **🎉 Since v1.5.0, the plugin will parse the `tailwind.config.js` file and use the correct values based on your own settings.**
>
> 👍 Most of [the new JIT mode features](https://tailwindcss.com/docs/just-in-time-mode#new-features) are also supported.
 
![detected-errors](https://user-images.githubusercontent.com/704026/117103443-ac1b0780-ad7a-11eb-9c17-41f0de3e4dc4.png)

## Installation

You'll first need to install [ESLint](http://eslint.org):

```
$ npm i eslint --save-dev
```

Next, install `eslint-plugin-tailwindcss`:

```
$ npm i eslint-plugin-tailwindcss --save-dev
```

[eslint-plugin-tailwindcss on npm](https://www.npmjs.com/package/eslint-plugin-tailwindcss)

## Usage

Add `tailwindcss` to the plugins section of your `.eslintrc` configuration file. You can omit the `eslint-plugin-` prefix:

```json
{
  "plugins": ["tailwindcss"]
}
```

Configure the rules you want to use under the rules section.

```json
{
  "rules": {
    "tailwindcss/classnames-order": 2,
    "tailwindcss/no-custom-classname": 2,
    "tailwindcss/no-contradicting-classname": 2
  }
}
```

Learn more about [Configuring Rules in ESLint](https://eslint.org/docs/user-guide/configuring/rules).

## Supported Rules

Learn more about each supported rules by reading their documentation:

- [`classnames-order`](docs/rules/classnames-order.md): order classnames by target properties then by variants (`[size:][theme:][state:]`)
- [`no-custom-classname`](docs/rules/no-custom-classname.md): only allow classnames from Tailwind CSS
- [`no-contradicting-classname`](docs/rules/no-contradicting-classname.md): e.g. avoid `p-2 p-3`, different Tailwind CSS classnames (`pt-2` & `pt-3`) but targeting the same property several times for the same variant.

## Upcoming Rules

- `no-redundant-variant`: e.g. avoid `mx-5 sm:mx-5`, no need to redefine `mx` in `sm:` variant as it uses the same value (`5`)

## Alternatives

I wrote this plugin after searching for existing tools which perform the same task but didn't satisfied my needs:

- [eslint-plugin-tailwind](https://www.npmjs.com/package/eslint-plugin-tailwind), not bad but no support (yet) for variants sorting
- [Headwind](https://marketplace.visualstudio.com/items?itemName=heybourn.headwind), only works within Visual Studio Code

## Contributing

You are welcome to contribute to this project by reporting issues, feature requests or even opening Pull Requests.

Learn more about [contributing to ESLint-plugin-TailwindCSS](CONTRIBUTING.md).
