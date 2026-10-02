# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some Oxlint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Oxc](https://oxc.rs)
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/)

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the Oxlint configuration

If you are developing a production application, we recommend enabling type-aware lint rules by installing `oxlint-tsgolint` and editing `.oxlintrc.json`:

```json
{
  "$schema": "./node_modules/oxlint/configuration_schema.json",
  "plugins": ["react", "typescript", "oxc"],
  "options": {
    "typeAware": true
  },
  "rules": {
    "react/rules-of-hooks": "error",
    "react/only-export-components": ["warn", { "allowConstantExport": true }]
  }
}
```

See the [Oxlint rules documentation](https://oxc.rs/docs/guide/usage/linter/rules) for the full list of rules and categories.

## Dashboard dependencies

Dependency setup only; the Vite starter remains in place. Stitch screens, routes,
query providers, application stores, and forms are not implemented yet.

- Styling: Tailwind CSS v4 through `@tailwindcss/vite`.
- Components: shadcn with the Radix Nova preset, Lucide icons, CSS theme variables,
  and `@/` aliases. Initialization includes the Button component and `cn` utility.
  Add components with `npx shadcn add <component>`.
- TanStack: React Router, Query, Table, and Virtual. Router's Vite plugin and
  Router/Query devtools are installed but not mounted or enabled yet.
- Client state: Zustand.
- Forms and validation: React Hook Form, Zod, and `@hookform/resolvers`.
- Supporting packages: date-fns, Sonner, class-variance-authority, clsx,
  tailwind-merge, and tw-animate-css.

TanStack Form and Store are intentionally not installed: React Hook Form and
Zustand own those responsibilities. Server-side TanStack Start is not needed for
this Vite SPA. The theme uses the `.dark` class; theme switching is not implemented.

Use `npm install`, `npm run dev`, `npm run build`, and `npm run lint`.
The generated shadcn Button exports `buttonVariants`, which currently produces
an Oxlint `react/only-export-components` warning.
