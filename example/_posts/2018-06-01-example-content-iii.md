---
layout: post
title: A Hybrid Network Combining Cnn and Transformer Encoder to Classify Mosquitoes Based on Wing Beat Frequencies
description: >
  A Hybrid Network Combining Cnn and Transformer Encoder to Classify Mosquitoes Based on Wing Beat Frequencies
image: 
  path: /assets/img/blog/arc1.png
  srcset:
    1060w: /assets/img/blog/arc1.png
    530w:  /assets/img/blog/arc1.png
    265w:  /assets/img/blog/arc1.png
related_posts:
  - example/_posts/2017-11-23-example-content-ii.md
  - /example/2012-02-07-example-content/
sitemap: false
---
---
## The reason for this project 
Whenever I visit places with mosquitoes around, I am the one who gets bitten a lot compared to others (My blood is tasty). At this time, I was taking my higher-level undergraduate classes as a junior in college, where I had to come up with project ideas for my courses. My brain whispered, "Why not make a machine to kill all the bloody mosquitoes?". The first thing I looked up was, will the world survive without mosquitoes? The answer is absolutely not! So killing only which bit me seems fair. Hence, the machine should be able to detect mosquitoes and kill them somehow. The detection part is okay, but the killing part by automation seems a bit dangerous as pointing lasers can be harmful if false positives occur in the system that can hurt humans. Finally, after much thought, I had to settle for building the first part of my idea and leave the killing to the mosquito-killing lamps. (You will be thrilled to know that the first part is as important if not more important than building the second one as you read this post.)

## The process


## Large Tables

| Default aligned |Left aligned| Center aligned  | Right aligned  | Default aligned |Left aligned| Center aligned  | Right aligned  | Default aligned |Left aligned| Center aligned  | Right aligned  | Default aligned |Left aligned| Center aligned  | Right aligned  |
|-----------------|:-----------|:---------------:|---------------:|-----------------|:-----------|:---------------:|---------------:|-----------------|:-----------|:---------------:|---------------:|-----------------|:-----------|:---------------:|---------------:|
| First body part |Second cell | Third cell      | fourth cell    | First body part |Second cell | Third cell      | fourth cell    | First body part |Second cell | Third cell      | fourth cell    | First body part |Second cell | Third cell      | fourth cell    |
| Second line     |foo         | **strong**      | baz            | Second line     |foo         | **strong**      | baz            | Second line     |foo         | **strong**      | baz            | Second line     |foo         | **strong**      | baz            |
| Third line      |quux        | baz             | bar            | Third line      |quux        | baz             | bar            | Third line      |quux        | baz             | bar            | Third line      |quux        | baz             | bar            |
| Second body     |            |                 |                | Second body     |            |                 |                | Second body     |            |                 |                | Second body     |            |                 |                |
| 2 line          |            |                 |                | 2 line          |            |                 |                | 2 line          |            |                 |                | 2 line          |            |                 |                |
| Footer row      |            |                 |                | Footer row      |            |                 |                | Footer row      |            |                 |                | Footer row      |            |                 |                |
{:.scroll-table}


## Code blocks

~~~js
// Example can be run directly in your JavaScript console

// Create a function that takes two arguments and returns the sum of those
// arguments
var adder = new Function("a", "b", "return a + b");

// Call the function
adder(2, 6);
// > 8
~~~


## Math
Lorem ipsum $$ f(x) = x^2 $$.

$$
\begin{aligned}
  \phi(x,y) &= \phi \left(\sum_{i=1}^n x_ie_i, \sum_{j=1}^n y_je_j \right) \\[2em]
            &= \sum_{i=1}^n \sum_{j=1}^n x_i y_j \phi(e_i, e_j)            \\[2em]
            &= (x_1, \ldots, x_n)
               \left(\begin{array}{ccc}
                 \phi(e_1, e_1)  & \cdots & \phi(e_1, e_n) \\
                 \vdots          & \ddots & \vdots         \\
                 \phi(e_n, e_1)  & \cdots & \phi(e_n, e_n)
               \end{array}\right)
               \left(\begin{array}{c}
                 y_1    \\
                 \vdots \\
                 y_n
               \end{array}\right)
\end{aligned}
$$


## Message boxes
**NOTE**: You can add a message box.
{:.message}

## Large text
You can add large text.
{:.lead}

## Large images
![Full-width image](https://via.placeholder.com/800x100){:.lead width="800" height="100"}

## Captions to images
![Full-width image](https://via.placeholder.com/800x100){:.lead width="800" height="100"}
A caption to an image.
{:.figure}

## Large quotes
> You can make a quote "pop out".
{:.lead}

## Faded text
I'm faded, faded, faded.
{:.faded}


[mm]: https://guides.github.com/features/mastering-markdown/
[ksyn]: https://kramdown.gettalong.org/syntax.html
[ksyntab]:https://kramdown.gettalong.org/syntax.html#tables
[ksynmath]: https://kramdown.gettalong.org/syntax.html#math-blocks
[katex]: https://khan.github.io/KaTeX/
[rtable]: https://dbushell.com/2016/03/04/css-only-responsive-tables/
