## step to reproduce

1. `cd main_package`
2. `pnpm install`

```bash
# expected behavior: linked file and source file have the same inode number
ls -i node_modules/pkg_no_postinstall/index.js
>77098466 node_modules/pkg_no_postinstall/index.js
ls -i ../pkg_no_postinstall/index.js
>77098466 ../pkg_no_postinstall/index.js

# unexpected behavior: linked file and source file have different inode number
ls -i node_modules/pkg_with_postinstall/index.js
>77110542 node_modules/pkg_with_postinstall/index.js
ls -i ../pkg_with_postinstall/index.js
>77098845 ../pkg_with_postinstall/index.js
```
