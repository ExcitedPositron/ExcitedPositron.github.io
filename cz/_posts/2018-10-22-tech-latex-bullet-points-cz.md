---
layout: postcz
title:  "Super odrážky v LaTexu"
date:   2018-10-22
excerpt: "Už žádné nudné pomlčky nebo kolečka, odrážky taky můžou mít osobnost."
techcz: true
comments: true
feature: /assets/img/posts/comp.png
---

Jsme zpět u mého oblíbeného latexu. Tentokrát vám chci ukázat jak vyměnit nudné body a pomlčky za slumíčka, kytičky nebo letadlo. Proč? No jen tak a navíc každá prezentace přeci může vypadat dobře a osobitě. Tak jak na to? Začneme z jednoduchého beamer dokumentu: 

{% highlight text %}
\documentclass[]{beamer}
\begin{document}
	\begin{frame}{}
	\begin{itemize}
		\item Obyčejná pomlčka
	\end{itemize}
\end{frame}
\end{document}
{% endhighlight %}

Nejdřív si musíme přidat účelové knihovny latexu (konkrétně enumitem a pifont) a hned to můžeme vyzkoušet. Já si taky ráda měním barvu svých pomlček, takže nejdřív definuji růžovou barvu (buď můžu použít už definované latexové barvy nebo použít jakoukoliv RGB barvu). Tady to je všechno hezky pohromadě:

{% highlight text %}
\documentclass[]{beamer}
\usepackage{enumitem}			% Tento balíček poskytuje ovládání tří zákládních prostředí: enumerate, itemize a description.
\usepackage{pifont}			% Na přístup k PostScript symbolům a Dingbats písmům.
\definecolor{pink}{RGB}{174,26,100}	% Můžete zadat jakoukoliv barvu, stačí zadat RGB hodnoty.

\begin{document}
	\begin{frame}{}
	\begin{itemize}[label={\color{pink}\Pifont{pzd}{\char40}}]	% Tady jenom zadejte svojí vybranou barvu a číslo symbolu pifont které si přejete použít jako pomlčku.
		\item Zajímavá pomlčka
	\end{itemize}
\end{frame}
\end{document}
{% endhighlight %}

A máme to. Jen se podívejte na rozdíl:

<figure class="half">
	<img src="/assets/img/posts/bullet1.png">
        <img src="/assets/img/posts/bullet2.png">
        <figcaption>Před a po použití zajímavé pomlčky.</figcaption>
</figure>

Abyste to použili v dokumentu několikrát, musíte vždy přípojit [label= ..] po každém \begin{itemize}. Tady jsem použila pomlčku číslo 40, což je letadlo, ale můžete si vybrat ze stovky neotřelých symbolů, záleží jen na vás.

<figure>
        <a href="/assets/img/posts/pifont.png"><img src="/assets/img/posts/pifont.png"></a>
        <figcaption>Pifont symboly.</figcaption>
</figure>

Já používám číslo 93 prakticky ve všech prezentacích, ať jde o pracovní prezentace nebo prezentace pro veřejnost. Mám to uložené jako šablonu ve svém editoru, takže si to nemusím pamatovat nebo pokaždé vyhledávat na internetu. Tak snad si je užijete tak jako já :)

Jaká je vaše oblíbená pomlčka? Je to obyčejné kolečko/pomlčka nebo něco osobitějšího?

<figure>
        <img src="/assets/img/posts/pres.png"></a>
        <figcaption>Ukázka mojí prezentace.</figcaption>
</figure>