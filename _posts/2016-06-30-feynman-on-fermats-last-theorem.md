---
layout:     post
title:      Feynman on Fermat's Last Theorem
date:       2016-06-30 11:21:29
summary:    Feynman on Fermat's Last Theorem
categories: jekyll pixyll
---

Richard Feynman was probably one of the most talented physicists of the 20th century. He was known for having a tremendous mathematical and physical intuition that allowed him to deconstruct complex concepts and approach problems from first principles. There are countless anecdotes that show Feynman’s genius, from his ability as an undergrad at MIT to use his own methods to solve seemingly untreatable integrals to coming up with his [own derivation of the Schrödinger equation](http://fermatslibrary.com/s/feynmans-derivation-of-the-schrodinger-equation) as a grad student in Princeton. While reading more about Feynman’s derivation of the Schrödinger equation in Schweber’s book [QED and the Men who made it](https://www.amazon.com/QED-Men-Made-Silvan-Schweber/dp/0691033277) I ended up finding a mention to an undated two-page manuscript written by Feynman about [Fermat’s Last Theorem](https://en.wikipedia.org/wiki/Fermat%27s_Last_Theorem). The manuscript doesn’t appear in the book but Schweber casts some light on Feynman’s approach which I will try to explain here in more detail. 

Fermat claimed in the 17th century that if \\(n\\) is a positive integer greater than
\\(2\\), the equation \\( x^n + y^n = z^n \\) does not admit integer non-trivial solutions, i.e. a solution where all three \\(x\\), \\(y\\) and \\(z\\) are non-zero. This statement is universally known as “Fermat’s Last Theorem” (or FLT), and the
equation therein is called “the Fermat equation”.

During more than three and half centuries this difficult problem received the attention
of many mathematicians of great fame, such as, among others, L. Euler, Legendre,
P.G.L. Dirichlet, E.E. Kummer, and more recently D.R. Heath-Brown, G. Frey, and
A. Wiles, who finally [solved the problem](https://en.wikipedia.org/wiki/Wiles%27s_proof_of_Fermat%27s_Last_Theorem).


Schweber doesn’t mention the date of the manuscript but since Feynman died in 1988 and Andrew Wiles published the proof of the Theorem in 1995 we know that when Feynman wrote it FLT was still one of the most famous open problems in mathematics. What’s interesting about the manuscript is that Feynman’s approach to the problem is purely probabilistic. He starts by calculating the probability that a number \\(N\\) is a perfect \\(n^{th}\\) power. To do this we need to calculate the distance between \\(\sqrt[n]{N}\\) and \\(\sqrt[n]{N+1}\\), where N is a large integer (I will explain later why we are doing this)
$$
d = \sqrt[n]{N+1}-\sqrt[n]{N} = \sqrt[n]{N}\sqrt[n]{1+\frac{1}{N}}-\sqrt[n]{N}=\sqrt[n]{N}\left(\sqrt[n]{1+\frac{1}{N}}-1\right)
$$
If we now use the power expansion \\( (1+x)^{k}= 1 + kx + \frac{k(k-1)}{2}x^2+...\\) for \\( -1< x<1\\)
$$
d =\sqrt[n]{N}\left(\left(1 + \frac{1}{n}\frac{1}{N} + \frac{\frac{1}{n}(\frac{1}{n}-1)}{2}\frac{1}{N^2}+...\right)-1\right)
$$
where \\(k=\frac{1}{n}\\) and \\(x=\frac{1}{N}\\). Note that we can use the power expansion since \\(\frac{1}{N}<1\\).
Taking the limit \\(N\rightarrow \infty\\) and preserving only the larger terms of the expansion we end up with
$$
d \approx \frac{\sqrt[n]{N}}{nN}
$$

Note that \\(d \approx \frac{\sqrt[n]{N}}{nN} =\frac{1}{n  \underbrace{\sqrt[n]{N}...\sqrt[n]{N}}\_{n-1 \text{ times}}} < 1\\) since \\(n>1\\), \\(\sqrt[n]{N}>1\\) and so \\(n\sqrt[n]{N}...\sqrt[n]{N} >1\\).

Feynman then writes “the probability that \\(N\\) is a perfect \\(n^{th}\\) power is \\(\frac{\sqrt[n]{N}}{nN}\\) ” . He didn’t explain how he got to this conclusion so here is what I think his thought process was. If \\(N\\) is a perfect power \\(N=z^n\\), there exists at least one integer ( \\(\sqrt[n]{N} = z \\)) in the interval \\([\sqrt[n]{N},\sqrt[n]{N+1}]\\). Since the distance between all consecutive integers is \\(1\\) the probability that \\([\sqrt[n]{N},\sqrt[n]{N+1}]\\) contains an integer is the ratio of the length of the intervals between two integers and the distance between \\(\sqrt[n]{N}\\) and \\(\sqrt[n]{N+1}\\): \\(\frac{d}{1}\\). A good way to visualize this is imagining a line where the distance between all consecutive integers is 1 meter. If someone drops a ruler of length d meter on top of the line the probability the ruler “hits” an integer is \\( \frac{d \text{ meter}}{1 \text{meter}}= d \approx \frac{\sqrt[n]{N}}{nN} \\).

Now in the case of FLT, \\( N=x^n + y^n \\) and so the probability that \\( x^n + y^n \\) is a perfect perfect \\(n^{th}\\) power is \\(\frac{\sqrt[n]{x^n + y^n}}{n(x^n + y^n )}\\). Of course this probability is for a specific \\(x\\) and \\(y\\) so if we want to calculate the total probability for any \\( x^n + y^n \\) we need to sum over all \\( x> \mathsf{x}\_{0} \\) and \\( y > \mathsf{y}\_{0} \\). Feynman chose to integrate the expression instead of summing it. My assumption is that he chose integrals because they are normally easier to handle than sums and the final result wasn’t going to be affected if instead of summing over integers we just integrate over all \\(x\\) and \\(y\\). 

Feynman also chose to do \\(\mathsf{x}\_{0}=\mathsf{y}\_{0}\\) . He ends up with the following expression:

$$
\mathsf{\int}\_{\mathsf{x}\_{0}}^{\infty}  \mathsf{\int}\_{\mathsf{x}\_{0}}^{\infty} \frac{1}{n}(x^n + y^n)^{-1+\frac{1}{n}} dx \\ dy = \frac{1}{n\mathsf{x}\_{0}^{n-3}}c_n \\ 
$$

$$
c_n = \mathsf{\int}\_{0}^{\infty}  \mathsf{\int}\_{0}^{\infty} (u^n + v^n)^{-1+\frac{1}{n}} du \\ dv
$$


To obtain \\(c_n\\) Feynman performs 2 changes of variables. The first one is \\(\theta=\frac{x-\mathsf{x}\_{0}}{\mathsf{x}\_{0}}\\) \\(\phi=\frac{y-\mathsf{x}\_{0}}{\mathsf{x}\_{0}} \\)

Doing the first change of variables:

$$
\mathsf{\int}\_{\theta(\mathsf{x}\_{0})}^{\infty} \mathsf{\int}\_{\phi(\mathsf{x}\_{0})}^{\infty}  f(x(\theta,\phi),y(\theta,\phi)) \left|\frac{\partial(x,y)}{\partial(\theta,\phi)}\right| d \theta \\ d \phi = 
$$
$$
=\mathsf{\int}\_{0}^{\infty}  \mathsf{\int}\_{0}^{\infty} \frac{1}{n} \mathsf{x}\_{0}^{1-n}((\theta + 1)^n + (\phi + 1)^n)^{-1+\frac{1}{n}} \mathsf{x}\_{0}^{2} d \theta \\ d \phi = 
$$
$$
=\frac{1}{n\mathsf{x}\_{0}^{n-3}} \mathsf{\int}\_{0}^{\infty}  \mathsf{\int}\_{0}^{\infty} ((\theta + 1)^n + (\phi + 1)^n)^{-1+\frac{1}{n}}  d \theta \\ d \phi
$$

where \\(\left|\frac{\partial(x,y)}{\partial(\theta,\phi)}\right|= \frac{\partial x}{\partial \theta}\frac{\partial y}{\partial \phi }-\frac{\partial x }{\partial \phi}\frac{\partial y}{\partial \theta} = \mathsf{x}\_{0}^2 \\) is the Jacobian and \\(\theta( \mathsf{x}\_{0})=\frac{\mathsf{x}\_{0}-\mathsf{x}\_{0}}{\mathsf{x}\_{0}} = 0\\) \\( \phi( \mathsf{x}\_{0} ) = \frac{\mathsf{x}\_{0}-\mathsf{x}\_{0}}{\mathsf{x}\_{0}} = 0 \\) . 

Finally we do the second change of variables \\(u = \theta + 1\\) and \\(v = \phi + 1\\)

$$
\frac{1}{n\mathsf{x}\_{0}^{n-3}} \mathsf{\int}\_{0}^{\infty}  \mathsf{\int}\_{0}^{\infty} ((\theta + 1)^n + (\phi + 1)^n)^{-1+\frac{1}{n}}  d \theta \\ d \phi = 
$$
$$
=\frac{1}{n\mathsf{x}\_{0}^{n-3}} \mathsf{\int}\_{1}^{\infty}  \mathsf{\int}\_{1}^{\infty} (u^n + v^n)^{-1+\frac{1}{n}}  d u \\ d v
$$



I think there’s actually a typo in the lower limits of the integral (\\(c_n\\)) that Feynman derived as they should be 1's and not 0's. Note that \\(u(0) = 0 + 1 = 1\\) and \\(v(0) = 0 + 1 = 1\\).


Finally we got an expression for the probability that \\( z^n=x^n + y^n \\) is an integer and we can calculate it for several \\(n\\)’s. Setting \\(\mathsf{x}\_{0}=2\\) we can see that the probability of there being integer solutions to \\( z^n=x^n + y^n \\) (\\(\frac{1}{n\mathsf{x}\_{0}^{n-3}} \mathsf{\int}\_{1}^{\infty}  \mathsf{\int}\_{1}^{\infty} (u^n + v^n)^{-1+\frac{1}{n}}  d u \\ d v\\)) does decrease with increasing \\(n\\). 

![](http://i.imgur.com/qDWuLPe.png)

<!-- http://i.imgur.com/zk4hixX.png -->

Feynman also knew about Sophie Germain’s result, who proved in the early 19th century that Fermat’s equation has no solution for \\(n \leq 100\\). 
Since it gets more and more difficult to find a solution as \\(n\\) increases, Feynman tried to calculate the probability of finding a solution to Fermat’s equation using the knowledge that there’s none for \\(n \leq 100\\).

For sufficiently large n (I invite readers to derive this limit)

\\(c_n \approx \frac{1}{n}\\)

Therefore the probability of finding a solution for a particular \\(n\\) is \\(\frac{1}{n^2\mathsf{x}\_{0}^{n-3}}\\) and consequently the probability of finding a solution for any \\(n>\mathsf{n}\_{0}=100\\) is \\(\int_{100}^{\infty} \frac{1}{n^2\mathsf{x}\_{0}^{n-3}} dn\\).
If we calculate the integral for \\(\mathsf{x}\_{0}=2\\)

$$
\int_{100}^{\infty} \frac{1}{n^2 2^{n-3}} dn \approx 	8.85 \times 10^{-34}
$$

which means that the probability is less than \\(10^{-31}\\)%. Feynman concluded: “for my money Fermat’s theorem is true”. This is of course not very formal from a mathematical standpoint and is far from the [real 110 pages long proof](https://www.math.ias.edu/~anindya/fermat.pdf) of FLT that took A.Wiles years to put together, notwithstanding it’s a really good example of Feynman’s scientific approach and genius. As Feynman used to say: 

<blockquote>
  <p>
    the main job of theoretical physics is to prove yourself wrong as soon as possible.
  </p>
</blockquote>  




















<!-- After the official release of the IPhone 5C and 5S I decided I wanted to buy an IPhone. However, like many people, I thought there were no groundbreaking changes between the new IPhone and the old IPhone 5, which led me to believe the best option would be buying a cheaper old version of the phone. Unfortunately, Apple had stopped selling the old IPhone 5 just after the new ones came out and so I looked at a couple of websites that were still selling them like Amazon, Ebay and a few more and tried to figure out which one was selling on average the cheapest devices. During my IPhone quest I ended up in a website called OLX (in this case the portuguese version of OLX since I am living in Portugal), which is a place where people can list and sell their items for free. One characteristic that stood out to me immediately in OLX was the easiness in contacting the seller, posing questions and making offers.To do that you just needed to fill out a simple form with your offer, email address, phone number and name and they would send an email to the seller with that information, without forcing you to register in the website. The seller would then have the option to decline or accept your offer via email. The second thing I noticed in OLX was the price variation. Unlike some of the other websites, which had pretty stable prices, OLX was showing a significant swings in the price of the listed IPhones. That was partially due to the fact that new and used IPhones were being sold at the same time, but a more interesting fact was that apparently a lot of sellers were having difficulties trying to figure out a price point to sell their IPhones, particularly after the release of the new ones. The combination of these two factors seemed to be the perfect opportunity to get a good deal. I thought a way to get a cheap IPhone was to approach the confused sellers and make them a few lowball offers with different emails to make them think the price they were asking was to high according to the market. Finally, I would make a not-so-low price offer that they would be inclined to take, thinking it was a good offer when compared to the other ones. Based on this assumption I quickly wrote a scrappy program in Python using Mechanize ( a library for automatic interaction with browsers ), that searched IPhone 5 in OLX, and did that for every potential IPhone found. I ran the program twice a day, searching for new IPhones and saving in a .txt file the ones I had already “contacted”. I was sending 5 emails per IPhone found, the first 4 where offering a price 70% lower than the one listed and the fifth one was offering a price 60% lower. The interval between sending the first and the last email was about 3 hours. Two weeks and almost 160 IPhones later, I found one guy that was originally selling an IPhone 5 for 225$ (with no contract and in perfect condition) and ended up selling me the phone for 90$!
 -->
