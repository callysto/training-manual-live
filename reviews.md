# Review Guide

This is a guide that outlines the review process for developed notebooks. The [first part](#part1) of the guide is for developers and outlines what you do after you complete a notebook. The [second part](#part2) of the guide is aimed at content reviewers (developers and/or subject matter experts) who will be assessing the content of notebooks developed for the Callysto project. Additionally this section will provide insight to developers on how your notebooks will be reviewed.

## Part 1: Notebook Reviews<a name="part1"></a>
Overall, there is a 2-step notebook review process:
1) Content review, then
2) Code review.

When a notebook has been developed and is ready to be committed to staging it will be first examined by a content reviewer and then by a code reviewer before it can be merged. Content and code reviewers are chosen based on their subject matter expertise and helps to ensure that only high quality content is pushed to staging.

### Notebook Review Process

_Huzzah i've completed my notebook!_ After the initial euphoria has worn off, developers should follow these steps to complete the content and code review processes.

#### Content Review Steps
1. Demo your notebook at a sprint demo meeting.
    * Note, this may not always be possible but you should always aim to share your work with your colleagues. At worst, demo your notebook to your supervisor or have a colleague demo for you.
1. Once you've demoed and incorporated initial feedback, in Jira, change the **Status** of your Story from `In-Progress` to `Resolved`.
1. Then, click `Create Sub-Task` in your Jira Story and enter "content review" in the **Summary** field.
    * The sprint coordinator will then assign a subject matter expert to review the content of your notebook.
1. The content reviewer will review the notebook for content and submit their comments back to developer. Once they have finished their review the **Status** of the Jira Sub-Task is changed from `In-Progress` to `Resolved`.
    * Review comments should be added directly to the Jira Sub-Task under the **Comments** section and/or the **Attachments** section if they are written in a separate file (e.g. markdown).
1. Once you have incorporated the content review feedback into your notebook, move the **Status** of the Jira Sub-Task from `Resolved` to `Closed (reviewed)`.

#### Code Review Steps
6. Once, the content review is completed, then you should create a pull request to merge your notebook branch to the staging branch in [GitHub](https://github.com/callysto/curriculum-notebooks).
    * [Git workflow overview](https://training.callysto.ca/coding/github-workflow).
1. A code review will then be done by one of the code reviewers. Once you have satisfied any requested code changes, your branch will be merged. When this occurs change your Jira Story **Status** from `Resolved` to `Closed (reviewed)`.


## Part 2: Guide for Content Reviewers<a name="part2"></a>
Congratulations on being selected as a _Callysto Content Reviewer_. Although it may seem thankless, your input at this point can make the difference between a notebook that seems great on the surface but perhaps doesn't quite connect with its intended audience. As a subject matter expert in this area it is important for you to point out both the technical flaws with the content (not code) and where there are opportunities to make the notebook better (e.g. more interactive).

### Content Review Checklist
To start, it is good practice to begin with an "Overall Summary" of your findings about the notebook before detailing the specific changes that should be made. The following are areas to pay attention to when content reviewing a notebook in detail for Callysto are:
1. Is the recommended grade level for the notebook displayed in the first cell underneath the title?
1. Has the document been spell checked and does it use proper grammar?
    - Does the notebook use full sentences, paragraphs and punctuation?  
1. Does the notebook keep the target audience in mind?
   - Is the grammar, narrative, examples, questions and exercises appropriate for the intended audience?
   - If at any point you as a reviewer are left confused by a sentence/explanation, that sentence/explanation needs work.
1. Does the notebook make sense?
   - Does the notebook have a coherent narrative?
   - Is the lesson/objective of the notebook obvious?
   - Is the notebook well organized?
      - Do sections lead well into each other - is there some logic connecting them?
   - Is the spelling and grammar correct/appropriate for the audience the notebook is intended for?
1. Does the notebook contain some sort of interactivity?
   - Widgets, animations, filling in segments of code etc.
1. Does the notebook demonstrate computational thinking in a way that is independent of understanding the underlying code?
   - See [computational thinking](computational_thinking.md)
   - Not applicable for notebooks where teaching the student to code is the lesson.
1. Does the notebook use an open data source to assist with the development of the notebook narrative and examples?
   - If you feel there is an open data source that could assist with the lesson, please let the developer know so that they may incorporate it
   - This may not be applicable in many cases.
   - Don't suggest incorporation of open data simply for the sake of incorporating open data.
1. Does the notebook complete its curriculum objective?


If the notebook you are reviewing has any of the issues listed above be *clear* and *specific*. For example instead of "your notebook is inappropriate for the intended audience" tell them *why*. Also tell them *where* the mistake or improvements are and provide actionable ways to fix it.


### Notebook Style Checklist
In addition to content, it is important to check to see if the notebook itself adheres to the Callysto style guide available [here](notebook-format.md), or [here](notebook-template.md) for a condensed version. A notebook should only pass content review if it has "good" style (or has a good reason not to have good style). Of course, you may be a teacher or outside the organization so you may not know what the Callysto style brand is. In this case, the style of the notebook can be updated via a separate Jira Sub-Task step such as a "style review" (To Be Determined).

Below is a list of common notebook aesthetic / style issues to watch out for:

1. Does the notebook use consistent title formatting?
   - Is the title of the notebook created with `# Title`?
   - Are main sections denoted with `## Section Title`?
   - Are subsections denoted with extra pound signs?
   - Is this done consistently?
1. Images
    - Do images possess a caption/is their relevance explained somewhere in adjacent text?
    - Does their placement make sense?
    - Is the image/font large enough to read?
1. Graphs
    - Is it compliant with the [infovis recommendations](https://github.com/callysto/training-manual/blob/master/markdown/infovis.md)?
    - Are all axes labelled?
      - With units (where applicable)?
    - Is the font large enough to read at a glance?
    - Is there a legend (where applicable)?
1. Tables
    - If the notebook contains data tables, is the column alignment consistent?
    - Is the table cut off due to the width of the window?
    - Do the column names make sense?
    - Do the column names contain units (where applicable)?
1. Inline code/code blocks in the markdown
    - Is inline code/variable references in the main body contained within back tics ( \` ) such that it renders as `variable`, so that it is distinguishable in the main body?
    - Are blocks of code to be discussed in triple back ticks ( \`\`\` ) such that they render similar to:
      ```python
      while True:
        # Infinite loops are okay in markdown
        print('''
              By adhering to basic style principles
              notebooks will be much more aesthetically pleasing.
              ''')
      ```
1. Mathematical typesetting
    - Are inline variables surrounded in dollar signs (for example`$x$`), such that it renders as $x$?
    - Are large expressions given their own line either with `$$ big math expression $$` or
     `\begin{equation}  
     big math expression
     \end{equation}`?
     - For example, something large and horrible like $$\left[-\frac{\hbar^2}{2m}\nabla^2+V(\vec r) + \int \frac{e^2n_\mathrm{s}\left(\vec r'\right)}{\left|\vec r-\vec r'\right|} \,{\mathrm d}^3r' + V_\mathrm{XC}[n_\mathrm{s}(\vec r)](\vec r)\right] \varphi_i(\vec r) = \varepsilon_i \varphi_i(\vec r)$$ should never appear in-line like this, and should be put in the proper equation environment.
     - If an equation is referenced in the discussion, is the equation numbered?
1. Colouring/fonts
    - Are any custom fonts/colours readable?
1. External links
    - Are they hidden with something like `[link to display](longlonglongwebsite.com)`?
         - Does the link work? Will the link still work in a few years or is the website likely to change?

In the case of these stylistic concerns, fixes should be easy and straightforward to communicate to the developer. Consistently upholding them makes our notebooks stylistically consistent between developers, visually pleasing, and easy to use.
