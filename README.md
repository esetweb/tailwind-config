# ESET Tailwind CSS Configuration

Common Tailwind config containing ESET brand tokens and other useful configurations.

## 1. Install Tailwind 4

**For Vite only projects**
Follow the official Tailwind CSS installation guide: [Tailwind CSS with Vite](https://tailwindcss.com/docs/installation/using-vite)

**For Nuxt projects:**
Plugin import may be slightly different - check the Nuxt documentation for the latest setup.

## 2. Install codestyle and class sorting

Install:

```bash
pnpm i @eset-gdd/code-styleguide-eslint-tailwind
```

Then add to your ESLint configuration:

```js
module.exports = {
  root: true,
  extends: ["@eset-gdd/code-styleguide-eslint-tailwind"],
};
```

This should enable automatic class sorting.

### Codestyle Troubleshooting

Return to this step after completing the installation if automatic class sorting doesn’t work.

1. Make sure ESLint is set as your default formatter:

2. `Ctrl + Shift + P` → Format Document With... → Configure Default Formatter → select ESLint.

3. If ESLint isn’t listed, ensure you have the ESLint extension

If the extension is installed but ESlint is not listed as a formatter, or automatic class sorting still fails, check the ESLint server output:

- `Ctrl + Shift + P` → ESLint: Show Output Channel.

If you see errors there, a fairly common cause is a version mismatch between your project’s ESLint and the installed codestyle package.

## 3. Install this package (tailwind configuration)

```bash
pnpm install @eset-gdd/tailwind-config
```

## 3. Replace your Tailwind import

During Tailwind installation, you created a CSS file with something like:

```css
/** tailwind.css / index.css / main.css file in your project  */
@import "tailwindcss";
```

**Replace this** with the shared ESET config:

```css
/** tailwind.css / index.css / main.css file in your project  */
@import "@eset-gdd/tailwind-config/index.css";
```

💡 **Keep this import in a separate CSS file** - it will come in handy later for IntelliSense configuration.

ℹ️ All Tailwind utilities are prefixed with `tw:` to avoid conflicts.

## 4. Install & configure Tailwind IntelliSense

Install the [Tailwind CSS IntelliSense extension](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss):

To enable both, the **ESET theme** and the **IntelliSense for the ESET theme**, add the following to your `.vscode/settings.json`:

```json
/** .settings.json */
{
  "tailwindCSS.experimental.configFile": "./src/styles/tailwind.css" // <-- add this line (relative path to file importing "@eset-gdd/tailwind-config/index.css")
}
```
