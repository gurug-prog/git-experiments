# Git experiments

This repository was created to explore some git features.

## Rebase

Here we have several branches for this demo: [rebase-demo](https://github.com/gurug-prog/git-experiments/tree/rebase-demo), [more-quick-feature](https://github.com/gurug-prog/git-experiments/tree/more-quick-feature), [features-to-rebase](https://github.com/gurug-prog/git-experiments/tree/features-to-rebase), [rebase-demo_after-rebase](https://github.com/gurug-prog/git-experiments/tree/rebase-demo_after-rebase).

**Step-by-step explanation:**

1. Firstly, we commit `file.txt` file with the very first feature directly into [rebase-demo](https://github.com/gurug-prog/git-experiments/tree/rebase-demo) branch.
2. Next we create a new branch [more-quick-feature](https://github.com/gurug-prog/git-experiments/tree/more-quick-feature) from rebase-demo and commit there a new feature.
3. We merge these branches doing

```
git checkout rebase-demo
git merge more-quick-feature
```

This will apply fast-forward strategy to the source and destination branches commits.

4. Do some features into [features-to-rebase](https://github.com/gurug-prog/git-experiments/tree/features-to-rebase) branched from [rebase-demo](https://github.com/gurug-prog/git-experiments/tree/rebase-demo). These features will be rebased in future.

5. Finally, we do

```
git checkout rebase-demo
git rebase features-to-rebase
```

And enjoy the result!

However, to make the result visible there was an extra step to rename the [rebase-demo](https://github.com/gurug-prog/git-experiments/tree/rebase-demo) branch: `git branch -m rebase-demo_after-rebase`.

6*. Push all these junk into the repo: `git push --all https://github.com/gurug-prog/git-experiments.git`. I personally prefer to use Personal Access Tokens that provided by GitHub, so I have [created one](https://github.com/settings/tokens) behind the scenes.
