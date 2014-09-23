# EML

EML stands for 'elements, modules, layouts'. All UI structures can be classified into one of these.

## Elements
Elements are non-divisible components. For the most part, these will consist of base HTML elements, though there is room for single-selector custom elements too. Use your judgment.

*Examples:*
```HTML
<button>
<input>
<h1>-<h6>
<body>
<small>
<div class='large'></div> // single-selector custom element
```

## Modules
Modules are reusable custom chunks of UI. These will typically consist of a single name-spaced wrapping element (e.g. `.project`) and will contain child structures (e.g. `.project-header`, `.project-body`, `.project-footer`) which house `elements` or other `modules`.

*Example:*
```HTML
<div class='project'> // module wrapper
  <div class='project-header'>Module terminus</div> // module component
  <div class='project-body'>Module terminus</div>   // module component
  <div class='project-footer'>Module terminus</div> // module component
</div>
```

In the above example, each module component represents the terminus of the Depth of Applicability. Within each of these stand-alone `elements` or `modules` can be housed.

## Layouts
