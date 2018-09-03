# Error in meteor when importing @material/ripple

Meteor fails to build correctly when importing "@material/ripple". The only change is the installation of the package (and 4 dependencys) and importing the package.

## Result in the Browser

Chrome shows a lot of error in the console. The first:
```Uncaught SyntaxError: Unexpected identifier```

For me this is Line 1011 in modules.js

``` import MDCComponent from '@material/base/component';```

## Update 2018-09-03
After symlinking the @material directory, ripple works.
```bash
mkdir -p imports/links
cd imports/links
ln -s ../../node_modules/@material .
cd ../..
meteor run
```
(Thanks to https://github.com/meteor/meteor/issues/10146#issuecomment-413331661 )

But more complex packages like MDCDialog won't work, see new import in client/main.js