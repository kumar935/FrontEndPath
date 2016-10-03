### Ways to start module

```javascript
//## 1
//here "moduleName" has to be included above then passed here
self.add(moduleName.instance({
    id: "details-container",
    options: {
        details: {},
        mode: "create"
    }
}));

//## 2
//here you just have to pass the name of module as as string in moduleName
this.$$.loadTemplate(
    this.path("olp.main.html"), 
    {
        moduleName: moduleName,
        nav: {
            module: e.params.module,
            tab: e.params.tab,
            context: ["/app", e.params.module, e.params.submodule].join("/")
        }
    }
)
```

### Router options

```javascript
router: jqrouter.map({
  "/normal/url": "useNormalUrl",
  "?queryParam=": "useQueryParam",
  "#/{hashUrl}": "useHashUrl"
})
```
