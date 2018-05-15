## Jupyter, Under the Hood

Jupyter used to be called IPython so Jupyter notebook files end with the extension .ipynb. If code you copied off stack exchange is not working you can try changing any instances of "IPython" to "Jupyter" (note: there are edge cases where only "IPython" will work).

When you open a Jupyter notebook document, the associated kernel (in our case a Python3 kernel) is automatically launched. When the notebook is executed (either cell-by-cell or with menu Cell -> Run All), the kernel  performs the computation and produces the results.
If you are on Callysto hub (you should be), the Python3 kernel will use remote Callysto hub CPU, RAM, and GPU for the computations it runs. Note that the RAM is not released until the kernel is shut-down.

Magics complicate this process by accessing other kernels, be wary because the magic kernels may use the user's local resources rather than the remote server resources. This is especially relevant when you are using JavaScript or WebGL for graphics rendering. Try to do all of your resource heavy computations in Python and then pass the results to your other kernels.

Internally, notebook documents are JSON data with binary values (base64) encoded. This allows them to be read and manipulated programmatically by any programming language. 

Notebooks can be exported to different static formats including HTML, reStructeredText, LaTeX, PDF, and slide shows (reveal.js) using Jupyter’s nbconvert utility.

Furthermore, any notebook document available from a public URL or on GitHub can be shared via nbviewer. This service loads the notebook document from the URL and renders it as a static web page. The resulting web page may thus be shared with others without their needing to install the Jupyter Notebook.

If you are interested in the low level details of Jupyter I suggest [these docs](https://jupyter-client.readthedocs.io/en/latest/messaging.html#messaging) although they are beyond the scope of most of the work we will be doing with notebooks.

### The Hub
Project Jupyter created JupyterHub to support many users, Callysto hub (hub.callysto.ca) is an example of a Jupyter hub. With JupyterHub you can create a multi-user Hub which spawns, manages, and proxies multiple instances of the single-user Jupyter notebook server. We are using docker and kubernetes. You will not need to know details of the deployment however, if you find any bugs with the server please report them!
