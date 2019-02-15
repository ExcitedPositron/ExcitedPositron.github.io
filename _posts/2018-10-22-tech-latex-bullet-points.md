---
layout: post
title:  "Cool Bullet Points in LaTex"
date:   2018-10-22
excerpt: "If you are bored of the generic circle or dash as a bullet point and want to give your presentation some personality."
tech: true
tag:
- latex
- physics
comments: true
feature: /assets/img/posts/comp4.jpg
i18n-link: bullet-tr
---

First we start from a basic beamer setup:

{% highlight text %}
\documentclass[]{beamer}
\begin{document}
	\begin{frame}{}
	\begin{itemize}
		\item Generic bullet point 
	\end{itemize}
\end{frame}
\end{document}
{% endhighlight %}
     
Now, first we need to add some latex packages (enumitem and pifont) and then we can try it out. I also like to change the color of my bullet points, so I will define a color pink (you can use the generic latex colors as well). Main work is 

{% highlight text %}
\documentclass[]{beamer}
\usepackage{enumitem}			% This package provides user control over the layout of the three basic list environments: enumerate, itemize and description. 
\usepackage{pifont}			% Gives you the access to PostScript standard Symbol and Dingbats fonts.
\definecolor{pink}{RGB}{174,26,100}	% You can pick whichever color you like, just put in its RBG values.

\begin{document}
	\begin{frame}{}
	\begin{itemize}[label={\color{pink}\Pifont{pzd}{\char40}}]	% Here you just select your color and then the number of pifont character you want to use as your bullet.
		\item Cool bullet 
	\end{itemize}
\end{frame}
\end{document}
{% endhighlight %}

And check out the difference:

<figure class="half">
	<img src="/assets/img/posts/bullet1.png">
        <img src="/assets/img/posts/bullet2.png">
        <figcaption>Before and after defining a cool bullet point.</figcaption>
</figure>


To use it multiple times in your document, you will have to include the [label= ..] after each \begin{itemize}. Here I used number 40 which is a plane, but there are loads of other cool characters, just pick your favorite.

<figure>
        <a href="/assets/img/posts/pifont.png"><img src="/assets/img/posts/pifont.png"></a>
        <figcaption>Pifont symbols.</figcaption>
</figure>

I use number 93 in all of my presentations these days. As I have it saved in my basic presentation layout, I don't need to remember all this or search on google every time I make a presentation, my bullet points always come out as pretty flowers (but still quite subtle). I hope you enjoy them as much as I do :)

<figure>
        <img src="/assets/img/posts/pres.png">
        <figcaption> Example of my presentation. </figcaption>
</figure>