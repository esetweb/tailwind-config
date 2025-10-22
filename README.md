# ESET Tailwind CSS Configuration

Common Tailwind config containing ESET brand tokens and other useful configurations.

## 1. Install Tailwind 4

**For Vite only projects**
Follow the official Tailwind CSS installation guide: [Tailwind CSS with Vite](https://tailwindcss.com/docs/installation/using-vite)

**For Nuxt projects:**
Plugin import may be slightly different - check the Nuxt documentation for the latest setup.

## 2. Install @eset-gdd/tailwind-config

```bash
npm install @eset-gdd/tailwind-config
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

## 5. Class Autosorting

Tailwind class autosorting is handled by the ESLint configuration `@eset-gdd/code-styleguide-eslint-tailwind` (installed automatically as a peer dependency).
