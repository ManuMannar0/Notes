This is a notebook, usefull when creating React app.
When you see "*", that is a non-react context or not-only.

When you are starting a project, ideas could be confused.
Reading this repo will help you.
Always learn this before start a project.
This content is always "work in progress".

##TOOLS

VsCode extensions 🔧

- Prettier (VsCode extensions)
- Live Server (VsCode extensions) *
- HTML CSS JS Support (VsCode extensions)

##APP

- ResponsivelyApp

##HTML

- follow this steps: react components -> grid/flex -> flex -> no div tag when is possible.
- in projects with very different layout between desktop and browser, follow this mindset:
    - let's start with the more components/element version (usually desktop version). Layout and styles.
    - for the simplest version (usually mobile) use conditional rendering. The component has to know the current version (mob/desk) from inside.
- all clickable element must be "button" or "a" tags. Avoid paragraph or others as possible
- don't put hard-coded class/id when inside return 
- don't put "props.anything" inside return 

##LOGIC & JS:

- write clean and mantainble code
- write for others developers
- split complex JSX return in smaller components
- use -> ()=>functionName() to be sure the function doesn't take prop..
- ..otherwise use a simple reference -> functionName
- always check if u can delete code. Less is more.
- always write autocommented code
- for keys's list (react only case): 
    - use internal object values or.. 
    - ..if there aren't useable values, concat that values in order to create secure keys or..
    - .. u can clone the object adding key with package like uuvd but do this:
        - const clonedObject = originalObject.map(item => ...item, id: uuvd()) 

##CSS

- follow this steps:
    - css with var from the beginning
    - use 'calc'
    - css files for:
        * VARS.scss divide with comment like margins, font sizes, colors, imgs sizes ec..
        * GENERAL.scss for tags
        * MEDIAQ.scss with no mediaQ on top and mediaQ on bottom. Mantain the same comments areas from VARS.scss.
    - stylize with "D_" for desktop version and "M_" for mobile.
- general advices:
    - use "sass" 
    - write scss in BEM
    - every component is a section with his "id" (ID, not class). All styles elements nested. 
    - layout grid (manage with grid-template, gap and padding) then flex
    - always check this mediaQ: 2560px / 1920px / 1440px / 1366p x / 1280px / 1200px / 1024px / 992px / 768px
    - write @media only screen and (max-width: resolution px) {}

- consider useing styled components: 
    - every styled component inside a single file
    - don't stylize "h1", stylize const H1 = styled.button`...`

##REACT

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
        - everything in react is a component 
        - always design abstract component
        - when a parent pass a prop to a child and that prop changes, the child is re-rendered
        - when an internal prop (inside a comp) change, the comp isn't re-rendered
        - if u want re-render the comp when a prop changes, that prop has to be a state
        - use redux toolkit with createSlice, useSelector, useDispatch
        - create components when that particular piece of component needs to be reused
        - when is possible pass only the necessary prop to the child, not the entire object
        - when is possible retrive the props destructuring

##MANIFEST 

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

##OPEN GRAPH

- 
- 
- 

##SERVER 

- avoid 404 from server when refreshing page. Add .htaccess file in public folder with this:
    RewriteEngine On
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteRule ^(.*)$ /index.html [L,QSA]

    this will redirect all requests to server to index.html.

##FINALLY CHECK

- check for duplicated css by inspector (pay attention). !!! I need better tool.. 
- check crossbrowser styles
- remove none used stuff (follow React yellow alerts or unused/usefull comments or styles)
- remember check tools usefull in https://www.dunplab.it/


# ...Have a nice code 👽

    
