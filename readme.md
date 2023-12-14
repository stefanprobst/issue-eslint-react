we are trying to run eslint --fix on `src/app.tsx`, with two rules from `eslint-plugin-react` enabled (see `package.json#eslintConfig` and `.vscode/settings.json`).

- running `pnpm eslint src/app.tsx --fix` works fine:
  ```tsx
	<button aria-disabled={true} className="test">Test</button>
	```

- opening `src/app.tsx` in vscode and pressing `ctrl+s` to save and apply `codeActionsOnSave` produces invalid jsx:
  ```tsx
	<button aria-disabled className="test"={true}>Test</button>
	```

note: when only one of the two rules in `.vscode/settings.json#eslint.codeActionsOnSave.rules` is enabled, everything works fine
