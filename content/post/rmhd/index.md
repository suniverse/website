---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Magnetic Fields in Relativistic MHD"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2019-11-05T20:41:43-05:00
lastmod: 2019-11-05T20:41:43-05:00
featured: false
draft: false
markup: mmark

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []

---
In relativistic MHD, the magnetic field 4-vector $b_{\mu}$
and electric field $e_\mu$ in the fluid frame is defined through the 4-vector $u^{\mu}$ and EM 2-form $F_{\mu\nu}$.
$$\begin{eqnarray}
b^\mu &=& u_{\nu}*F^{\mu\nu}\\
e^\mu &=& u_{\nu}F^{\mu\nu}
\end{eqnarray}$$
where $*$ means the Hodge-dual of the 2-form.
It is obvious that $u_{\mu}e^{\mu}=0$ and $u_{\mu}e^{\mu}=0$.

MHD condition requires that $$e^{\mu}=0=u_{\nu}F^{\mu\nu}$$.
Using the antisymmetric tensor, we have
$$\begin{equation}
b^{\mu} = \frac{1}{2}\epsilon^{\mu\nu\kappa\lambda}u_{\nu}F_{\lambda\kappa}.
\end{equation}$$

Contract with $$\epsilon_{\mu\alpha\beta\gamma}$$ on both sides, and using the equality from (3.50h) Misner, Thorn, Wheeler
$$\begin{equation}
\delta^{\nu\kappa\lambda}_{\alpha\beta\gamma} = -\epsilon^{\mu\nu\kappa\lambda}\epsilon_{\mu\alpha\beta\gamma}.
\end{equation}$$

$$\delta^{\nu\kappa\lambda}_{\alpha\beta\gamma} $$ takes the value $$1$$ if $$\nu\kappa\lambda$$ is an even permutation of $${\alpha\beta\gamma}$$, and $$-1$$ for odd permutation, $$0$$ otherwise.

Hence,
$$\begin{equation}
\epsilon_{\mu\alpha\beta\gamma}b^{\mu} = -\frac{1}{2}\delta^{\nu\kappa\lambda}_{\alpha\beta\gamma}u_{\nu}F_{\lambda\kappa}.
\end{equation}$$
Now contract both sides with $$u^{\alpha}$$, and using the fact that $$u^{\mu}u_{\mu}=-1$$,$$u_{\nu}F^{\mu\nu}=0$$, only nonzero term on the right hand side come from $$\alpha=\nu$$, therefore
$$\begin{equation}
F_{\beta\gamma}=\epsilon_{\beta\gamma\alpha\mu}u^{\alpha}b^{\mu}.
\end{equation}$$

$$\begin{eqnarray}
*F^{\mu\nu}&=&\frac{1}{2}\epsilon^{\beta\gamma\mu\nu}\epsilon_{\beta\gamma\alpha\rho}u^{\alpha}b^{\rho}\\
&=&-\delta^{\mu\nu}_{\alpha\rho}u^{\alpha}b^{\rho}\\
&=&-(\delta^{\mu}_{\alpha}\delta^{\nu}_{\rho}-\delta^{\nu}_{\alpha}\delta^{\mu}_{\rho})u^{\alpha}b^{\rho}\\
&=&b^{\mu}u^{\nu}-b^{\nu}u^{\mu}
\end{eqnarray}$$

There might be a difference in sign in the last expression which does not matter. 
The Maxwell $$*F^{\mu\nu}_{;\nu}=0$$ is not affected by a minus sign on both sides. 
The fluid equation $$T^{\mu\nu}_{;\nu}=0$$. 
$$\begin{equation}
T^{\mu\nu}_{EM} = F^{\mu\alpha}F_{\nu\alpha}-\frac{1}{4}g^{\mu\nu}F_{\alpha\beta}F^{\alpha\beta}
\end{equation}$$
is quadratic in $$F^{\mu\nu}$$.