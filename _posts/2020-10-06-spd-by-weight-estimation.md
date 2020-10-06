---
title: Stochastic Process Discovery By Weight Estimation
layout: post
tags: ["stochastic process mining","stochastic process discovery","stochastic Petri nets","estimators"]
---
 
A focus of my current research is Stochastic Process Mining, ie, automatically discovering and analyzing process models incorporating probability from organizational event logs. One aspect of this newish area is stochastic process discovery, and I have a new paper out on this with colleagues Sander Leemans and Moe Thandar Wynn. It explores six new techniques for weight estimation with existing control flow discovery techniques like Fodina or Split Miner, outputting Generalized Stochastic Petri Nets, but using only the stochastic weighting. Some of the estimation techniques are straightforward, others less so, and they show the size of the potential solution space: just as there are many control-flow discovery algorithms, it's useful for there to be multiple stochastic process discovery algorithms in the toolbox as well. We term this approach "estimators" and ran an experimental evaluation that shows they are of comparable quality to an important existing technique \(Rogge-Solti et al, 2015\) (though narrower in outputs), generally faster, and apply to a broader range of event logs. 

Another aspect of interest for those in the field is applying new stochastic process conformance measures available in recent years, including Earth Movers' and Entropy measures (Leemans et al, 2019; Leemans & Polyvyanny, 2020).

For more detail, see _Stochastic Process Discovery By Weight Estimation_ [paper](/papers/burke_leemans_wynn_spdiscover_we_20200929.pdf) and [slides](/papers/burke_spdiscover_we_slides_pqmi2020.pdf). There are also publicly available [source code and result files](https://github.com/adamburkegh/spd_we/).

I had the opportunity to present this research at the Process Querying, Manipulation and Intelligence Workshop 2020 this week, accompanying the ICPM 2020 conference. 

---

_References_

Burke, A, Leemans, S.J.J. and Wynn, M.T. (2020). Stochastic Process Discovery By Weight Estimation.  International Workshop on Process Querying, Manipulation, and Intelligence 2020. In print.

Burke, A, Leemans, S.J.J. and Wynn, M.T. (2020). Report On Stochastic Process Discovery By Weight Estimation Experimental Results. Technical report. 

Leemans, S. J. J., Syring, A. F., & van der Aalst, W. M. P. (2019). Earth Movers’ Stochastic Conformance Checking. In T. Hildebrandt, B. F. van Dongen, M. Röglinger, & J. Mendling (Eds.), Business Process Management Forum (Vol. 360, pp. 127–143). Springer International Publishing. 

Leemans, S. J. J., & Polyvyanyy, A. (2020). Stochastic-Aware Conformance Checking: An Entropy-Based Approach. In S. Dustdar, E. Yu, C. Salinesi, D. Rieu, & V. Pant (Eds.), Advanced Information Systems Engineering (pp. 217–233). Springer International Publishing. 

Rogge-Solti, A., & Weske, M. (2015). Prediction of business process durations using non-Markovian stochastic Petri nets. Information Systems, 54, 1–14. https://doi.org/10.1016/j.is.2015.04.004



