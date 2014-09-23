# EML

EML stands for 'elements, modules, layouts'. All UI structures can be classified into one of these.

The EML directory structure looks like this (though, EML is primarily concerned with Components):
```JS
styles
  |- 00-library
  |- 01-config
  |- 02-components
      |- 00-elements
      |- 01-modules
      |- 02-layouts
```

## Library
Library contains any third-party party dependancies.

## Config
Config is where all global variables are defined in addition to any plugin configuration.

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