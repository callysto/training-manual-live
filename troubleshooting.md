# Troubleshooting

Steps to go through if it is not working:
+ Google.
+ Turn the kernel off and then on again.
+ Try incognito mode. Jupyter is nicer in incognito mode because browser caches will sometimes cause issues, especially the way Chrome does browser caching. Keep in mind however that the final notebook will need to be fully operational outside of incognito/private browsing.
+ Try a different browser.
+ Use the "inspect" tool built into your browser (ctrl-shift-i for Chrome).
+ Try messaging the slack, you will probably get a fast answer there and your fellow developers can help you.
+ If you are still stuck reach out to the appropriate person.

## Specific Issues

If you are using JavaScript `require` try switching it to `requirejs`. `require` sometimes stores JS in the cell's metadata which persists even after a restart and cache clear. `requirejs` *seems to* avoid this issue.

---

If you are getting the error "IOPub data rate exceeded" try to downsize what you are processing. We have upper bounds to avoid things like infinite loops crashing the servers. If you know that what you need to be processing is large you can contact cybera  to have your data rate limit increased.

---

JavaScript is naturally asynchronous, while Python is not. This will cause problems when passing variables between these languages.

e.g. A variable that has not yet been initialized by JavaScript will be inaccessible to later Python code. Often this manifests during a "Run All" command sent to the kernel.

---

Travis failing unexpectedly due permissions issues when loading external files may be caused by notebooks attempting to write to files. At the moment we discourage notebooks writing to files, if possible find a way around the notebook writing to the file. If it is necessary for your notebook to write to a file please reopen issue [#77](https://github.com/callysto/curriculum-notebooks/issues/77).

---

If only one of multiple widgets is working check if they are both pushing data to the same `svg` object. This can be caused by Javascript loading that is not protected by a function. This results in consistent name spacing between the files being over written by the _last_ declaration. Developers to need to wrap animations like this in functions, or they need to be aware that variable declarations _are not safe_ between files once they are loaded into Jupyter.

---

Loading D3 inside the notebook with `<script>` tags require the cells to be run twice in order for any javascript modules to be loaded in time - unless all your javascript is in the same cell (un-imported from an external file and under a `%%javascript` magic). Packages like `d3` need to be included with something like

```js
requirejs.config({
    paths: { 
        'd3': ['//cdnjs.cloudflare.com/ajax/libs/d3/3.5.6/d3'], 
    },                                       
});

require(['d3'], function(d3) { what you want your script to do} )
```

inside the actual `.js` file _not_ inside the notebook.
