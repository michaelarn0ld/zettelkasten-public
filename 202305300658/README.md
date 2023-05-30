# Bootstrap Svelte
Start a new Svelte application with:
```
npm init vite <PROJECT_NAME> -- --template svelte
```
Ref: https://vitejs.dev/guide/

Afterwards, get rid of all the excess that comes with the barebones install. I
will probably end up creating some python script that I can run inside of the 
generated project that will go ahead and clean up the minimal bloat that is
associated.

Install dependencies:
```
npm install
```

To bootstrap a development env:
```
npm run dev
```

To build production distribution:
```
npm run build
```

For Vim development, I found the plugins to be helpful:
```
Plug 'othree/html5.vim'
Plug 'pangloss/vim-javascript'
Plug 'evanleck/vim-svelte', {'branch': 'main'}
```
Ref: https://github.com/evanleck/vim-svelte

## Tags
#svelte #frontend #ui
