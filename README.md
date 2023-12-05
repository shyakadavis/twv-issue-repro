## Reproducing the issue

```bash
pnpm install
```

```bash
pnpm dev
```

## File to look at

```text
/src/lib/components/ui/button/index.ts
```

## Error

As I was preparing this repro, I got a better understanding of the issue.

One of the default variants is commented out.

Just as it is right now, before doing anything else, notice that intellisense works only for those lines up to the commented out variant. Anything below that is not recognized.

Uncommenting it will cause intellisense to stop working only for the lines below it.

In the past, I had set the complex arbitrary values inside the `base` key, meaning that intellisense would stop working for the entire file.

Go ahead and try pasting this at the end of the `base` key:

```ts
shadow-[4px_4px_0px_rgba(0,0,0,1)]
```

## Expected behavior

Intellisense should work for all lines; regardless of the order of the variants or the complexity of the tailwind arbitrary values.
