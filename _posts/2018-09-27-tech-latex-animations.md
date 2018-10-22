---
layout: post
title:  "Animations in LaTex"
date:   2018-09-11
excerpt: "How to move your latex slides"
tech: true
tag:
- latex
- physics
- animations
comments: true
feature: /assets/img/posts/dog2.jpg
---


I love animations in presentations. They can make complex processes understandable while keeping the presentation entertaining. Lets look at this animation of electrical charges behaviour. It shows the attraction of positive / negative charge and the repulsion of a positive / positive charge. It is a known concept to many so I think if it is a bit fun looking, even the very knowledgable person can be at least amused.

Ok lets get into it. I will start with a simple template and show you how to work your animation. Here is the basic latex template:

{% highlight text %}
\documentclass[]{beamer}
\begin{document}
\begin{frame}{Charged particles}
\end{frame}
\end{document}
{% endhighlight %}

Then we add the package animate.sty (which might not be in your basic latex packages, so you might have to download it, for example <a href="https://ctan.org/pkg/animate">here</a>). This will allow you to use \animategraphics to load your images. 

{% highlight text %}
\documentclass[]{beamer}
\usepackage{animate}
\begin{document}
\begin{frame}{Charged particles}
\begin{center}
\animategraphics[loop,width=0.9\textwidth]{3}{particle_}{1}{7} 
\end{center}
\end{frame}
\end{document}
{% endhighlight %}

The PNG images need to be in the format image_#.png so that you specify the start # and the end #, in this case I have images particle_1.png up to particle_7.png. The parameter {3} defines the number of images shown per second. 

In the end, it is important to open the pdf in Acrobat Reader, otherwise, the animation won't work.

<figure>
        <img src="/assets/img/posts/2018-10-22-particle/ss1.png">
</figure>

This is the resulting animation, showing opposite charges attract and same charges repel each other. It's not the best quality animation, but for me easily and quickly produced in Inkscape. For my explanation, it is understandable and entertaining. 

<figure class="animated_gif_frame">
        <img src="/assets/img/posts/2018-10-22-particle/charged-particles.gif" />
</figure>

