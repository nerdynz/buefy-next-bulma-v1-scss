
> :warning: WIP: Not all scss files are included right now.. Use this as an example as I work through them


# Development 
1. run `pnpm sass` and it will test a build and show any errors.
2. uncomment lines in _index.scss
3. work through the errors by manually searching through node_modules/buefy/sass (its quite readable once you get a feel for the import/use structure)

# Getting Started

1. pnpm add bulma
2. clone this repo
3. pnpm link -g from this cloned repo (might eventually get on NPM)
4. pnpm link -g buefy-next-bulma-v1-scss in **your repo**
5. add bulma scripts to your package json in **your repo**
   
```
"build-bulma": "sass --load-path=node_modules my-bulma-project.scss my-bulma-project.css",
"start": "npm run build-bulma -- --watch"
```

7. add a my-bulma-project.scss file with the following (rename it. i just want a consistant example)
   
```
@use "sass:color";

// Set your brand colors
$purple: #8a4d76;
$pink: #fa7c91;
$brown: #757763;
$beige-light: #d0d1cd;
$beige-lighter: #eff0eb;

// Path to Bulma's sass folder
@use "bulma/sass" with (
  $family-primary: '"Nunito", sans-serif',
  $grey-dark: $brown,
  $grey-light: $beige-light,
  $primary: $purple,
  $link: $pink,
  $control-border-width: 2px,
  $input-shadow: none
);

// Import the Google Font
@import url("https://fonts.googleapis.com/css?family=Nunito:400,700");


// Import buefy-next-bulma-v1-scss  
@import 'buefy-next-bulma-v1-scss';
```
8. run `pnpm build-bulma` with the above import and it should spit out a good css file
9. include that css file in your project


Bulma sass starting point here 
[Bulma With Sass Example](https://bulma.io/documentation/customize/with-sass/#create-your-sass-file)


## Notes
**Dont use the scss file instead build and import the resulting css fil**


## DEV Notes
breakpoints are now include mx.breakpoint (mx is aliased - bulma does this)
`@include tablet` becomes  -> `@include mx.breakpoint("tablet")`
