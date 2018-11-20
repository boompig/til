You can push to multiple origins simultaneously by adding multiple push URLs. Detailed instructions can be found [here](https://gist.github.com/rvl/c3f156e117e22a25f242)

```
git remote set-url --add --push origin git@github.com:muccg/my-project.git
git remote set-url --add --push origin git@bitbucket.org:ccgmurdoch/my-project.git
```

This is very useful for pushing to Github and Heroku at once.
