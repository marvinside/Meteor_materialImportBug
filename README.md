# Error in meteor when importing @material/ripple

Meteor fails to build correctly when importing "@material/ripple". The only change is the installation of the package (and 4 dependencys) and importing the package.

## Result in the Browser

Chrome shows a lot of error in the console. The first:
```Uncaught SyntaxError: Unexpected identifier```

For me this is Line 1011 in modules.js

``` import MDCComponent from '@material/base/component';```
