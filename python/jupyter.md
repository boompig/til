# Jupyter

## Jupyter Lab

I'm now using Jupyter Lab notebooks. This extension is great: https://github.com/matplotlib/ipympl

## Quick Reference

I always Google these things:

How to show longer strings in pandas tables

```
pd.set_option('display.max_colwidth', 255)
```

Make figures (graphs) larger: pass `figsize` as an argument into either the `.figure` or the `.plot` function. Example:

```
x.plot.bar(x='occupation_en', y='count', legend=0, figsize=(12,5))
```

