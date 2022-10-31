# Reproduction for [turbo#2517](https://github.com/vercel/turbo/issues/2517)

```
> pnpm i
> pnpm turbo run build
```

The build will succeed but it won't build the widget package, despite it being part of the pnpm workspace.

The widget package is built as expected when it's moved to `widgets/widget-a`, instead of there being a symlink there (`widgets/widget-a -> ../submodules/widget-a`):

```
> rm widgets/widget-a
> mv submodules/widget-a widgets/widget-a
> pnpm i
> pnpm turbo run build
```
