# EML

EML stands for 'elements, modules, layouts'. All UI structures can be classified into one of these.

The EML directory structure looks like this (though, EML is primarily concerned with Components):
```JS
styles
  |- 00-config
  |- 01-utility
  |- 02-components
      |- 00-elements
      |- 01-modules
      |- 02-layouts
```

## Config
Configuration files (e.g. grid system, heading scale, etc.).

## Utility
Config is where all global utility classes are defined.

## Components

### Elements
**Elements** are non-divisible components. For the most part, these will consist of base HTML elements, though there is room for single-selector custom elements too. Use your judgment.

*Examples:*
```HTML
<button>
<input>
<h1>-<h6>
<body>
<small>
<div class='large'></div> // single-selector custom element
```

### Initial Build
Here's a copy/paste snippet that can be used to help build out this basic directory strutcture:

```
mkdir 00-config 01-utility 02-components 02-components/00-elements 02-components/01-modules 02-components/02-layouts
touch 00-config/_colors.styl
touch 01-utility/_helpers.styl
touch 02-components/00-elements/_button.styl
touch 02-components/01-modules/_header.styl
touch 02-components/02-layouts/_modal.styl
```

### Modules
**Modules** are reusable custom chunks of UI. These will typically consist of a single name-spaced wrapping element (e.g. `.project`) and will contain child structures (e.g. `.project-header`, `.project-body`, `.project-footer`) which house **elements** or other **modules**.

*Example:*
```HTML
<div class='project'> // module wrapper
  <div class='project-header'>Module terminus</div> // module component
  <div class='project-body'>Module terminus</div>   // module component
  <div class='project-footer'>Module terminus</div> // module component
</div>
```

In the above example, each module component represents the terminus of the Depth of Applicability of the module—the module ends there. Within each of these, stand-alone **elements** or **modules** can be housed.

### Layouts
**Layouts** are standalone compositions of various application/site content. Layouts have a singlular wrapping element and are comprised of any number of compnonent elements.

Example:
```HTML
<div class="app">
  <div class="app-header"></div>
  <div class="app-body"></div>
  <div class="app-footer"></div>
</div>
```

Principles used for modules also apply to layouts, but we distinguish them from modules for the sake of clarity. There will inevitably be a very limited number of layouts as compared to modules. This is a good thing.

## Naming Conventions

### Modules

Modules are given a name with camel case formatting.

```
.moduleName
  background red
  border-radius .2em
```

### Submodules

Submodules must be prefixed with it's parent module name and separated by a hyphen.

```
.moduleName-header
  font-size 3em
  color green
```

### Modifiers

Modifiers can change modules or submodules based off of a given state.

```
.moduleName-header.is-active
  display block
```

### Subclasses

Subclasses can change modules or submodules

```
.moduleName.huge
  font-size 10em
.moduleName-header.wrap
  white-space wrap
```
