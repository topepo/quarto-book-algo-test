# An algorithm

A code chunk just for fun!


::: {.cell}
::: {.cell-output .cell-output-stdout}

```

Call:
lm(formula = mpg ~ disp, data = mtcars)

Coefficients:
(Intercept)         disp  
   29.59985     -0.04122  
```


:::
:::


## Setup

I used `quarto add leovan/quarto-pseudocode` to add the extension.

They suggest an inclusion via `include-in-header` in `_quarto.yml`:

```         
<script>
MathJax = {
  loader: {
    load: ['[tex]/boldsymbol']
  },
  tex: {
    tags: "all",
    inlineMath: [['$','$'], ['\\(','\\)']],
    displayMath: [['$$','$$'], ['\\[','\\]']],
    processEscapes: true,
    processEnvironments: true,
    packages: {
      '[+]': ['boldsymbol']
    }
  }
};
</script>
<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml-full.js" type="text/javascript"></script>
```

They also suggest adding

```         
filters:
  - pseudocode
```

## An example algorithm

``` pseudocode
#| label: alg-resampling
#| html-indent-size: "1.2em"
#| html-comment-delimiter: "//"
#| html-line-number: true
#| html-line-number-punc: ":"
#| html-no-end: false
\begin{algorithm}
\caption{Resampling for performance estimation.}
\begin{algorithmic}
\State $D$: training set of predictors $X$ and outcome $y$
\State $B$: number of resamples
\State $f()$: modeling function including preprocessing
\Procedure{Resample}{$D, B, f()$}
  \For{$b =1$ \To $B$}
    \State Partition $D^{train}$ into $D_b^{model}$ and $D_b^{pred}$.
    \State Train model $f$ on the analysis set to produce $\widehat{f}_{b}(D_b^{model})$.
    \State Generate assessment set predictions $\widehat{y}_b$ by applying model $\widehat{f}_{b}$ to $D_b^{pred}$.
    \State Estimate performance statistic $\widehat{Q}_{b}$.
  \EndFor 
  \State Compute reampling estimate $\widehat{Q} = \sum_{b=1}^B \widehat{Q}_{b}$.
  \Return $\widehat{Q}$.
\Endprocedure
\end{algorithmic}
\end{algorithm}
```

We'd reference this using @alg-resampling. 

Here's another code chunk!

A code chunk just for fun!


::: {.cell}
::: {.cell-output .cell-output-stdout}

```
[1] 0.6321206
```


:::
:::
