## Side Navigation Menu

**cc-side-nav** are exported as an es module thus you would need a bundler to use it. It is also written in
Typescript so it can be directly used with a typescript project as well

### NavContext 

To render conditionally an item can get the context which contains the following attributes:

| property   |      type      |  description |
|------------:|-------------:|------:|
| expanded | boolean  | if this side nav default opened |
| collapsible | boolean  | collapsible option will be enabled/disabled |
| dataSource | array  | Navigation items  |
| onNavLinkClicked | event  | Call back events to Application  |
| onNavLinkExpanded | event  | Call back events to Application  |

## Below is an example on how to use it.

```html
<cc-side-nav expanded [collapsible]="true" [dataSource]="appRoutes" 
                  (onNavLinkClicked)="onNavLinkClicked($event)"
                  (onNavLinkExpanded)="onNavLinkExpanded($event)"></cc-side-nav>
```
## Below is an dataSource structure.
```javascript
export class RouteMapNode {
  children?: RouteMapNode[];
  name: string;
  type?: string | null;
  pathName: string;
  component: string;
  isDefault: boolean;
  path: string;
  iconText: string;
  fontSet: string;
  activeClass: string;
}
```
## Sample dataSource 
```javascript
export const appRoutes = [
    { 
        name: 'Home',
        children:[],
        iconText: 'home',
        fontSet: 'icomoon'
    },
    {
        name: 'Theme',
        route: '/theme',
        iconText: 'droplet',
        fontSet: 'icomoon',
        children: [
            {
                name: 'Icon Overview',
                pathName: 'icon',
                component: IconComponent,
                isDefault: false,
                path: '/icon',
                iconText: '',
                fontSet: ''
            }]
    }];
```
