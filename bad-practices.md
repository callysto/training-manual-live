# Bad Practices, Mistakes and How to Avoid Them
Many of these are common mistakes we have seen in Jupyter notebook development. Feel free to add more to this file.

## Use textContent not innerHTML, for text inputs
In JS functions if you have a DOM element (divs, svg, etc.) .innerHTML, if you get information from a form, it executes when it reads the form data. Susceptible to XSS attacks. [Use textContent instead](https://stackoverflow.com/questions/16860287/security-comparison-of-eval-and-innerhtml-for-clientside-javascript), for more info you can read: https://stackoverflow.com/questions/21311299/nodevalue-vs-innerhtml-and-textcontent-how-to-choose

## Iframes
Iframes are good if you need to contain things, but if you want to access variables in those things then iframes are bad. Instead use magics and html and javascript function calls from the display library. It produces cleaner code too.

## System time
Do not make programs that are dependant on system time.

## Infovis
No pie charts or spaghetti plots. Avoid clutter, and volume comparisons. See the infovis section of the manual for more indepth information.

## Use Python for heavy processing
JS uses the browser aka local, resources. Python uses the remote Callysto Hub resources. Ideally you will do any heavy processing in Python and then pass the results to JS. Try to avoid doing large processing tasks with the user's local resources.

## Do not parse HTML with regex
[Do not parse HTML with regex](https://stackoverflow.com/questions/1732348/regex-match-open-tags-except-xhtml-self-contained-tags) or other level 2 languages.
