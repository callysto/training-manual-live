# Welcome To Callysto

The Callysto project is a collaboration between [the Pacific Institute of Mathematical Sciences (PIMS)](https://www.pims.math.ca/) and [Cybera Inc](https://www.cybera.ca/) and is funded by the Government of Canada through the [CanCode program](https://www.ic.gc.ca/eic/site/121.nsf/eng/home). Our overall goal is to bring elements of computational thinking into the K-12 curriculum by developing showcase curriculum modules using Jupyter technology and training K-12 teachers to use these modules in the classroom.

## The Purpose of This Guide

This training guide is meant to be a resource for Callysto creators and developers to get started on building content for the Callysto project.

### Why **Callysto**?

The open-source Jupyter technology is an important aspect of how we are delivering the curriculum materials we are developing. [Callysto](<https://en.wikipedia.org/wiki/Callisto_(moon)>) is a moon of Jupiter and the `y` is our way of aligning ourselves to the larger [Project Jupyter](http://jupyter.org/).

### Developing for the Callysto Project

Callysto developer will commit to and create selected curriculum content modules in Jupyter notebooks. Our subject matter expert advisors will help to review the created content and provide any feedback.

## Things to Keep in Mind While Developing Content

When creating a notebook, keep your target audience in mind. For example, if your notebook is meant for Grade 5 students, the reading level and instructions should be no higher than Grade 5 (preferably a grade or two lower). You can check the reading level of text using some online tools (such as [this one](https://www.perrymarshall.com/grade/)), through tools built into [Word](https://support.office.com/en-us/article/get-your-document-s-readability-and-level-statistics-85b4969e-e80a-4777-8dd3-f7fc3c8b3fd2) and [Docs](https://support.google.com/docs/answer/39003?hl=en-GB), or with a [Python library](https://github.com/shivam5992/textstat).


As a Callysto creator and developer you may be far removed from the K-12 experience. Continuously ask yourself "Would someone who knows absolutely nothing about anything contained within this topic understand the explanation I've given?". It is imperative that you are clear and explicit in your explanations - but also in a way that your audience can understand.

## When Developing Code

In a similar way, when writing Python code you should aim for simplicity. For example

```Python
def GCD(a, b):
    if isinstance(a, float) or isinstance(b,float):
        print("Those numbers are not integers!")
        return None

    while b:
        a, b = b, a % b
    return a
```

For someone with coding experience, that's fairly easy to understand. Run through a loop until `a mod b` is zero and you've the greatest common denominator.  And it works every time! There's even error handling! Over all that's a pretty versatile function, and a neat little piece of code.

But now imagine you have never seen Python before. You don't know what `def` means, you have no clue what `while` does. What is `isinstance`? What's a `float`? `if`? Why is it spaced all funny? A percent sign? Even if this function was heavily commented, it might still be somewhat unapproachable for beginners. How would you go about constructing a simple Python example that would find greatest common divisors?

There might not be a great way to implement this particular example for a beginner audience. A better example might be to also introduce the idea of equivalent fractions, and ask them to find if two fractions are equivalent:

```Python
# Change the numbers in each fraction then run this cell to check if they are equivalent fractions.
# If the two fractions are equivalent, the word "True" will be printed under this cell.
# Can you find three pairs of equivalent fractions?

10/5 == 124/62
```

While that might be less interesting code, it is more approachable for someone with no Python experience.

That being said, if you can create an intuitive, interesting, and interactive widget or visualization that requires some more "advanced" coding, you are also free to do so. Remember to consider your audience however.

### Conclusion

When creating notebooks for the Callysto project, be aware of the skill set of your audience. There will definitely be occasions where you can get more involved in the code and the explanations in cases like high school content. Even so, a lot of the people this content will be used by will have little to no experience with Python or even the subject you're trying to teach. We've summarized a few flexible guidelines for you to keep in mind:

1. **Keep it simple**.
2. Depending on what you are creating, you may need to write more complicated code. That's probably fine, but consider breaking it into small interactive chunks.
3. A simple example is almost always superior to a complicated one. Work your way up to the complicated examples.
4. Explain with words more than you explain with code.
5. Comment your code.
6. Comment your code some more.
7. If all you want is an interactive widget and not to use the code itself as a teaching tool, consider moving the code to a helper function in a separate file.
8. Always be conscious of your audience.