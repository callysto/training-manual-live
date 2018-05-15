# Welcome To Callysto

The Callysto project is a collaboration between the Pacific Institute of Mathematical Sciences (PIMS) and Cybera Inc and is funded by the Government of Canada through its CanCode program. Our overall goal is to bring elements of computational thinking into the K-12 curriculum by developing showcase curriculum modules using Jupyter technology and training K-12 teachers to use these modules in the classroom.

## The Purpose of This Guide

This training guide is meant to be an all-in-one resource for Callysto creators and developers to get started on building content for the Callysto project.

### Why **Callysto**?

The open-source Jupyter technology is an important aspect of how we are delivering the curriculum materials we are developing. [Callysto](https://en.wikipedia.org/wiki/Callisto_(moon) is a moon of Jupiter and the `y` is our way of aligning ourselves to the larger [Project Jupyter](http://jupyter.org/).

### Developing for the Callysto Project

Callysto development teams will consist of 2 to 6 people:
* a university (PIMS) professor.
* 1 - 4 student developers (Callysto creators and developers).
* an external K-12 teacher (or subject matter expert) advisor.

Callysto development teams will commit to and create selected curriculum content modules in Jupyter notebooks during iterative 2-week sprint periods. Once created, our external subject matter expert advisors will help to review the created content and provide any feedback for the development team.

## Things to Keep in Mind While You're Developing Content
   Every time you create a notebook for the Callysto project, it is of the utmost importance that you keep your target audience in mind. As each notebook may be aimed at a different grade/experience level, you will need to be consciously aware of that during the notebook creation process. If your notebook is meant to teach content from the fifth grade, then tailor your introductions in such a way that someone in the fifth grade can understand. Unfortunately that is not an easy task, but it is of vial importance not to "Principal Skinner" your notebooks (YouTube link below):

  <iframe
    width="560"
    height="315"
    src="https://www.youtube.com/embed/HMqZ2PPOLik"
    frameborder="0"
     allowfullscreen>
  </iframe>




   As a Callysto creator and developer, you're undoubtedly so far removed from the K-12 experience that unlike Principal Skinner: You are out of touch. Say these words out loud "I am out of touch". You need to keep this in mind that for every notebook you create, and adapt your writing/teaching style accordingly. Continuously ask yourself "Would someone who knows absolutely nothing about anything contained within this topic understand the explanation I've given?". Almost certainly, in regards to the first draft of your notebook the answer to that question will be no. Something that is now second nature to you from years of experience around either the subject matter and Python (or both), is likely to be completely foreign to a K-12 student who has never seen a line of code before. It is imperative that you are clear and explicit in your explanations - but also in a way that your audience can understand.

 ## Example... Example

 Suppose you're creating a notebook describing finding common denominators of numbers to someone in the third grade. A very bad way to describe that to someone in third grade would be:


 > Common denominators typically of interest in many algebraic and integer functions, where integer functions $$f$$ have the following property
>
>$$ f:  I \rightarrow \mathbb{Z} $$
>
> Without losing generality one can state that...

while a discussion at that level is acceptable at the post secondary and academic level, that sentence and notation will mean exactly nothing to someone in the third grade. At the third grade level, a more suitable way to describe common denominators may read something more like this:
> Two fractions that have the same number on the bottom of the fraction  have a "common denominator" -- which means the number on the bottom of each fraction is the same. For example the fractions
>
>$$ \frac{10}{8} \; \text{ and } \; \frac{5}{8} $$
>
>both have a common denominator of 8. Common denominators....



Certainly, the above is an absolutely absurd example. No one would write that for a notebook meant for the third grade. However keep that example in mind for when you're writing any codes. Maybe during your discussion of common denominators, you introduce the idea of a greatest common denominator between two numbers. You might be tempted show how to find greatest common denominators using Python. Maybe you want to write a nice general function to find the greatest common denominator between two numbers, and suppose you come to the following solution:

```Python
def GCD(a, b):
    if isinstance(a, float) or isinstance(b,float):
        print("Those numbers are not integers!")
        return None

    while b:
        a, b = b, a % b
    return a
```

Where for anyone with experience, that's a pretty easy code to understand. Run through a loop until `a mod b` is zero and you've the greatest common denominator.  And it works every time! There's even error handling! Over all that's a pretty versatile function, and a neat little piece of code. Not to mention we can give the students that function, and ask them to find the greatest common denominator between two numbers and write the resulting functions!

But now imagine you have never seen Python before. You don't know what `def` means, you have no clue what `while` does. What is `isinstance`? What's a `float`? `if`? Why is it spaced all funny? A percent sign? All bets are off. While that is a handy function to someone with experience, much like with the math example, it's basically hieroglyphics to your audience. Even if this function was heavily commented, it would still be very unapproachable for someone in third grade. How would you you go about constructing a python example that would find greatest common divisors in Python to someone in third grade?

Trick question. There isn't a great way to implement this particular example for a third grade audience. A better example might be to also introduce the idea of equivalent fractions, and ask them to find if two fractions are equivalent like so

```Python
# If you change the numbers of each fraction you can ask Python if those
# numbers are equivalent fractions! If you press Ctrl and Enter on your
# keyboard at the same time, the computer will run the code at the bottom
# of this cell

# If two fractions are equivalent fractions, the word "True" will be
# printed under this cell, and if they're not, the word "False" will be printed.
# Can you find three pairs of equivalent fractions? It might help to write them
# down first!

10/5 == 124/62
```

Where that's certainly a less interesting snippet of code, it's a lot more approachable and intuitive if someone has no experience with Python, and for someone in the very early stages of elementary/middle school.

With all that said: if you can create an intuitive and interesting interactive widget/visualization that requires some more "advanced" coding, you are absolutely free to do that. A lot of the time more interactive widgets and functionality will make explaining what you hope to teach many times easier. In this case take advantage of the ability to hide blocks of code and only give the student access to the widget itself.

### Conclusion/Take Away

When you're creating notebooks for the Callysto project, you need to be hyper aware of the skill set of your audience. There will definitely be occasions where you can get more involved in the code and the explanations in cases like high school content. Even so, a lot of the people this content will be used by will have little to no experience with Python or even the subject you're trying to teach. Unfortunately that means you'll likely have to change how you typically develop content from how you normally would. Below we've summarized a few flexible guidelines for you to keep in mind while developing content

1. **Keep it simple**.
2. Depending on what you're hoping to/asked to create, you may need to write more complicated code. That's probably fine. Depending on the audience either hide it behind an interactive widget, or break it down into digestible and interactive (even if it's just running it) chunks.
3. A simple example is almost always superior to a complicated one. Work your way up to the complicated examples.
4. Explain with words more than you explain with code.
5. Comment your code.
6. Comment your code some more.
7. If all you want is an interactive widget and not to use the code itself as a teaching tool, hide the code block from the student.

In summary, be conscious of who the audience of your content will be, and don't be a Principal Skinner.



### Pre-requisite notebooks

Some examples of developed Callysto curriculum module notebooks can be found in this [GitHub repository](https://github.com/callysto/callysto-sample-notebooks). These specific examples should help you get inspired and started: [Investigating Conductivity](https://github.com/callysto/callysto-sample-notebooks/blob/master/notebooks/Science/investigating_conductivity.ipynb), [Radioactive Decay](https://github.com/callysto/callysto-sample-notebooks/blob/master/notebooks/Physics/Nuclear.ipynb), [Flipping Coins](https://github.com/callysto/callysto-sample-notebooks/blob/master/notebooks/Math/FlippingCoins.ipynb), [Interactive Geometry](https://github.com/callysto/callysto-sample-notebooks/blob/master/notebooks/Math/Interactive%20Geometry.ipynb), [American Revolution](https://github.com/callysto/callysto-sample-notebooks/blob/master/notebooks/Social_Sciences/History/American_revolution_with_animated_slider.ipynb) and [Shakespeare and Statistics](https://github.com/callysto/callysto-sample-notebooks/blob/master/notebooks/Social_Sciences/Humanities/Shakespeare_and_Statistics.ipynb).
