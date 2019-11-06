---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Eliminating Pressure for Incompressible MHD"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2019-11-05T20:41:43-05:00
lastmod: 2019-11-05T20:41:43-05:00
featured: false
draft: false

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
In the formulation of Elsasser's variables $\mathbf{U} = \mathbf{v}+\mathbf{b}$ and $\mathbf{W} = \mathbf{v}-\mathbf{b}$,

\begin{eqnarray}
	&&\partial_t \mathbf{U} = -(\mathbf{W}\cdot\nabla)\mathbf{U}-\nabla p,\\
	&&\partial_t \mathbf{W} = -(\mathbf{U}\cdot\nabla)\mathbf{W}-\nabla p,\\
	&&\nabla\cdot\mathbf{U} = \nabla\cdot\mathbf{W} = 0.
\end{eqnarray}

For undisturbed fluid $\mathbf{U} = V_A$ and $\mathbf{W} =- V_A$. Introducing small purturbation $\mathbf{U} = V_A+\mathbf{u}$ and $\mathbf{W} = -V_A+\mathbf{w}$

\begin{eqnarray}
	&&\partial_t\mathbf{u}-V_A\partial_z\mathbf{u} = -(\mathbf{w}\cdot\nabla)\mathbf{u}-\nabla p,\\
	&&\partial_t\mathbf{w}+V_A\partial_z\mathbf{w} = -(\mathbf{u}\cdot\nabla)\mathbf{w}-\nabla p.\\
\end{eqnarray}

Taking the divergence of above equations
\begin{eqnarray}
	\nabla p  = \nabla\cdot[(\mathbf{w}\cdot\nabla)\mathbf{u}].
\end{eqnarray}

In the Fourier space
\begin{eqnarray}
	k^2 \tilde{p} = (\mathbf{k}\cdot\tilde{\mathbf{u}}(\mathbf{k}_1))(\mathbf{k}_1\cdot\tilde{\mathbf{w}}(\mathbf{k}_2))\delta(\mathbf{k}_1+\mathbf{k}_2-\mathbf{k}).
\end{eqnarray}

Therefore the Fourier transformation of $\nabla p $ gives
\begin{eqnarray}
	\mathbf{k}p = (\hat{\mathbf{k}}\cdot\tilde{\mathbf{u}}(\mathbf{k}_1))(\mathbf{k}\cdot\tilde{\mathbf{w}}(\mathbf{k}_2))\delta(\mathbf{k}_1+\mathbf{k}_2-\mathbf{k}),
\end{eqnarray}
where the incompressible condition $\mathbf{k}_2\cdot\tilde{\mathbf{w}}(\mathbf{k}_2)=0$ is used.

Taking the Fourier transform of the perturbed equations and defining $\omega_k = V_A k_z$

\begin{eqnarray}
	(\partial_t-i\omega_k)\tilde{\mathbf{u}}(\mathbf{k}) = -\frac{i}{8\pi}\int d^3 k_1 d^3 k_2\; (\tilde{\mathbf{u}}(\mathbf{k}_1)-\hat{\mathbf{k}}(\hat{\mathbf{k}}\cdot\tilde{\mathbf{u}}(\mathbf{k}_1))(\mathbf{k}\cdot\tilde{\mathbf{w}}(\mathbf{k}_2))\delta(\mathbf{k}_1+\mathbf{k}_2-\mathbf{k})
\end{eqnarray}

\begin{eqnarray}
	(\partial_t-i\omega_k)\tilde{\mathbf{w}}(\mathbf{k}) = -\frac{i}{8\pi}\int d^3 k_1 d^3 k_2\; (\tilde{\mathbf{w}}(\mathbf{k}_1)-\hat{\mathbf{k}}(\hat{\mathbf{k}}\cdot\tilde{\mathbf{w}}(\mathbf{k}_1))(\mathbf{k}\cdot\tilde{\mathbf{u}}(\mathbf{k}_2))\delta(\mathbf{k}_1+\mathbf{k}_2-\mathbf{k})
\end{eqnarray}
