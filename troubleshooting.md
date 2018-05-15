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
