# *Documentation!!!*
**Please notice that this will be well documented after completion!!!**

Required Node version: **`14`**  
Default creds: **`{email: admin@cashier.dev, pass: admin1234}`**  
This REST API working on: **`localhost:8000/v1`**,  
Package Manager: **`yarn`**  

**Before coding run:**
 - **``yarn``** install packages
 - **``yarn prepare``** for husky development
 - **``yarn dev``** for dev
 - **``yarn build``** for prod
 - **``yarn test``** for jest test
 - **``node .nuxt\server.js``** for deploy
 
# *Components Creation*

### layouts:
We use layout to serve content (client / dashboard), ``each layout has it's own components inside (./components/client) or (./components/dashboard)``.

**if you would like to add new global components for each layout would be inside this folders.**

### pages:
We use page to serve components for each route ```(./pages/)``` for client or ``(./pages/admin)`` for dashboard.
**each page should have it's own components inside ``./components/client/[widgets or partia or / for globals]`` or ``./components/dashboard/[widgets or partia or / for globals]``**

### elements:
We use custom elements for most use case inside ``./components/elements``:  

`<x-link>`: for links.
`<x-img>`: for serving and caching image in Webp or any other format.
`<x-icon>`: for icons (all types).
`<x-alert>`: for alerts.
`<x-table>`: for tables.

# *APIs Creation*
We use Repository Pattern **( an abstraction of the Data Access Layer )**  for APIs call.

**Inside ``/modules/repos`` directory**

each file name must be **``{ModuleName}Repository.ts``** so for Auth module we use  *``AuthRepository.ts``*

each file must use this structure :
```typescript
import  type { AxiosInstance, RequestConfig} from  '@/types'

const  resource: string = '/resource-path'
export  default ($api: AxiosInstance) => ({
  all(config: RequestConfig) {
    return  $api.get(`${resource}`, config)
  },

  create(config: RequestConfig) {
    return  $api.post(`${resource}/create`, config)
  },

  delete(config: RequestConfig) {
    return  $api.delete(`${resource}/delete`, config)
  },
})
```

# *Plugins Creation*
***Soon!***

# *Important!!!*
Try to follow the same coding style and pattern and naming convention =>
    
-   Code MUST use 2 spaces for indenting, not tabs.
    
-   There MUST NOT be a hard limit on line length; the soft limit MUST be 120 characters; lines SHOULD be 80 characters or less.
-   Opening braces for classes MUST go on the next line, and closing braces MUST go on the next line after the body.
    
-   Opening braces for methods MUST go on the next line, and closing braces MUST go on the next line after the body.
    
-   Visibility MUST be declared on all properties and methods;  `abstract`  and  `final`  MUST be declared before the visibility;  `static`  MUST be declared after the visibility.
    
-   Control structure keywords MUST have one space after them; method and function calls MUST NOT.
    
-   Opening braces for control structures MUST go on the same line, and closing braces MUST go on the next line after the body.
    
-   Opening parentheses for control structures MUST NOT have a space after them, and closing parentheses for control structures MUST NOT have a space before.
