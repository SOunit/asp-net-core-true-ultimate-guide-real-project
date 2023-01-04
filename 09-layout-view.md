# execution order

- Views -> Controller -> Shared
- Views / folder
  - `_ViewImports.cshtml`
  - `_ViewStart.cshtml`
  - ControllerName / folder
    - `_ViewImports.cshtml`
    - `_ViewStart.cshtml`
    - `ViewName.cshtml`
  - Shared / folder
    - `_LayoutView.cshtml`

# js and css is available

- merge finish in server so js and css is available in browser
