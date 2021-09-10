## REACT (not only) web app notes
This is a notebook, usefull when creating React app.
When you see "*", that is a non-react context or not-only.

When you are starting a project, ideas could be confused.
Reading this repo will help you.
Always learn this before start a project.
This content is always "work in progress".


# TOOLS

VsCode extensions 🔧

- Prettier (VsCode extensions)
- Live Server (VsCode extensions) *
- HTML CSS Support (VsCode extensions)

App 📀

- ResponsivelyApp


# ADVISE

- Organise your folders to find everything at the glance 
- Follow this steps: grid/flex -> flex -> no div as possible -> style with var -> separate components


Html:

- in desktop/browser very different layout, follow this mindset:
    - let's start with the more components/element version (usually desktop version). Layut and styles.
    - for the simplest version (usually mobile) use conditional rendering. The component know if what device from inside.
    - stylize with "D_" for desktop version and "M_" for mobile.
- no "div" tag when is possible
- all clickable element must be "button" or "a" tags. Avoid paragraph or others as possible
- don't put hard-coded class/id when inside return 
- don't put "props.anything" inside return 

Logic:

- write clen and mantainble code
- write for others developers
- split complex JSX return in smaller components

Css:

- follow this steps:
    - css with var from the beginning
    - css files for:
        * VARS.scss divide with comment like margins, font sizes, colors, imgs sizes ec..
        * HTML.scss for tags
        * MEDIAQ.scss with no mediaQ on top and mediaQ on bottom. Mantain the same comments areas from VARS.scss.
    - Import in MEDIAQ.scss all styles you want control  from components.
- general advices:
    - use "sass" 
    - write scss in BEM
    - every component is a section with his "id" (ID, not class). All styles elements nested. 
    - avoid nesting class/id when is possible 
    - all scss files components in components folder with node-scss pkj installed, or "scss" folder in root and use -> npx sass --watch scss:css 
    - layout grid then flex
    - style with var
    - always check this mediaQ: 2560px / 1920px / 1440px / 1366p x / 1280px / 1200px / 1024px / 992px / 768px

Styled component:

- consider useing styled components (every component style inside the component folder)
- don't stylize "h1", stylize const myH1 = styled.button`...`

![alt text](./stylesSetup.jpg)

React:

- insert this in package.json under private, to be sure the build will be ok:
    "homepage": "."
- React setup:
    - add jsconfig.json file with:
        {
            "compilerOptions": {
                "baseUrl": "src"
            },
            "include": ["src"]
        }
    "src" is absolute path now.
    - git modules in src folder. 
        add submodule:
            git submodule add -b master [indirizzo git modulo] src/[cartella da creare per modulo] && git submodule init.
        removev submodule:
            git submodule deinit src/[cartella modulo] && git rm src/[cartella modulo]. 
    - mindset:
        - everything is a component
        - always design abstract component
        - use children props with components composition in order to pass the data flow up and down the tree, whenever there is a simple related tree
        - business logic away from UI components with custom hooks or, in the Redux reducers if you use it
        - create components when that particular piece of component needs to be reused
        - the right way for passing data is passing props. 
            For fast and smalls projects you can pass the entire object. 
            For maintainable projects do this: 
                pass props, not entire object -> <InnerComponent name={object.name} image={object.image} />
                you can also do this -> <InnerComponent {...pick(object, 'name', 'image')} />
                if there are numerous props you can picked as this -> <InnerComponent object={pick(object, 'name', 'image')} />

        - use useReducer whenever possible instead of useState (except for primitives)
        - use React Query or Redux toolkit to work with asyncronus data; it guarantees the separation of concernes between global client state and global asyncronus state
    - var declaration:
        - if possible follow this order -> id/class, declaration id/class, props, conditional, inside components, use 

Manifest: 

- <link rel="manifest" href="%PUBLIC_URL%/manifest.json" /> in index

Favicon:

- use https://realfavicongenerator.net/
- add package created in ??? 
- add this in manifest:    
    - "icons": [
        {
            "src": "favicon.ico",
            "sizes": "64x64 32x32 24x24 16x16",
            "type": "image/x-icon"
        }
    ]

Open Graph:

- 
- 
- 

Server: 

- avoid 404 from server when refreshing page. Add .htaccess file in public folder with this:
    RewriteEngine On
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteRule ^(.*)$ /index.html [L,QSA]

    this will redirect all requests to server to index.html.

Finally, check:

- check for duplicated css by inspector (pay attention). !!! I need better tool.. 
- check crossbrowser styles
- remove none used stuff (follow React yellow alerts or unused/usefull comments or styles)
- remember check tools usefull in https://www.dunplab.it/

Better:

- use auto-renderizeing* components to provide a better code
- always take a look at your price quotation to be sure you did all works

# ...Have a nice code 👽

    
