# A high-level intro to Object-Oriented Programming (OOP) by contrasting it with the common way that early learners begin to structure their code

A programming language "<mark>paradigm</mark>" (pronounced: "pair-ah-dime") is **an overall approach to organizing your code**. As you have been exploring the online world of software developers, you are most likely to have heard of these (if any):

- Object-Oriented Programming (OOP)
- Functional Programming (FP)
- Procedural Programming (PP)

Much of the conversation about these approaches causes you to think of them as competitors, but in fact most professional codebases in active development today are a combination of more than one of the above approaches.

Today, we're going to discuss two of the above paradigms (approaches to organizing your code), and I think you'll find that you have been doing one of them all along.

## Procedural Programming

<mark>**Procedural** Programming</mark> is the approach of organizing your code according to the logical **process** you are aiming to achieve. You might think of it as "process-oriented programming" or "step-oriented programming." And this is what you've been doing the whole time.

Consider the code below:

```js
    let coinState = 0

    function coinFlip () {
        const headsOrTails = calculateRandomOneOrZero()
        coinState = headsOrTails
    }

    function coinStatetoString () {
        if (coinState === 1) {
            return "Heads"
        } else {
            return "Tails"
        }
    }
```

This is a *procedural* approach to the Coin object. Instead of grouping our coin logic and our coin data together, we have organized our code according to our normal intuition of:

- the importance of each step, and 
- the order in which each step needs to be completed.

And this makes a lot of very good sense. The resulting code becomes a representation of the above meanings, in a linear way, top-to-bottom — like a TODO list.

Procedural programming makes a lot of sense *within* each function, but it is prone to getting confusing as the code grows lengthy. Why? Because not everything occurs in an absolutely linear set of steps.

A user, for example, could click a button at any time. You might use some of your functions in multiple very different areas of your code. Some of your code might need to run at irregular times, instead of predictable times.

So this linear, step-by-step approach was created as a natural by-product of your sense of the relative importance and logical flow of your code, but starts to lose its linear shape (its primary benefit) the larger and more complex your code grows. Your code becomes very interdependent.

Very soon you have what developers humorously (and frequently) call "<mark>spaghetti code</mark>":  

![](https://i.imgur.com/FUxFhoI.png)

In the image above, think of each red line as a relationship between two parts of yours code. This relationship is known as "<mark>coupling</mark>." When your code gets "knotted up" by all these interdependent relationships, as shown in the image above, we call it "highly coupled."

To be fair, it is possible to get "spaghetti" in any programming paradigm, but Procedural Programming, while *extremely useful in small doses,* is especially prone to it.

## Comparing Procedural to Object-Oriented Programming

So, Procedural Programming:

- Organizes your code around the logical steps needing to be completed.
- This is very practical.
- But it has the eventual side-effect of relationships (couplings) between different sections of your code being scattered and almost disorganized around your codebase.

In contrast, Object-Oriented Programming:

- Organizes your code *around the relationships* which are needed to accomplish the goal,
- At the risk of developers focusing so much on building software which accurately and concisely describes the relationships that they build things which are too abstract and impractical.

The best overall approach, in my opinion, is probably using both paradigms for their strengths, using them to balance each other.

So at the beginning, OOP asks, "What are the most tightly-related concepts in our application?" and how do we build **objects** which represent these relationships.

So, refactored with Object-Oriented goals, the above "coin" code might be grouped together like so:

```js
const coin = {
    state: 0,
    flip: function() {
        const headsOrTails = calculateRandomOneOrZero()
        this.state = headsOrTails
    },
    toString: function() {
        if (this.state === 1) {
            return "Heads"
        } else {
            return "Tails"
        }
    },
```

Compare the two code examples to start forming an intuition about the distinction between the two paradigms and how they think about organizing your thoughts in order to solve challenges.

There is a lot more to be said on this subject. But for now, please watch Mosh's excellent [7-minute introduction to Object-Oriented Programming](https://www.youtube.com/watch?v=pTB0EiLXUC8).

## Further resources

- Read: [Object-Oriented JS (MDN)](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_JS)
