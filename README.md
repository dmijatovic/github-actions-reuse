# Github reusable actions

More complex experiments with github actions:

- reusable workflows
- passing variables between steps

## Reusable workflows

Official documentation can be [found here](https://docs.github.com/en/actions/using-workflows/reusing-workflows)

Usefull video is [thisone](https://www.youtube.com/watch?v=lRypYtmbKMs)

Note! The workflows cannot be at some other location other that the root of workflows folder. So the only location to have reusable workflows is ./.github/workflows. On the other hand shared workflows can reside in a different repository. To use them that repo need to have checkbox set to allow using the workflows by other repos.

### Summary

For reusable workflow the action type should be `workflow_call`. You can use other triggers but then it might happend to trigger reusable action more than once. Therefore my conclusion is to create "pure" reusable actions that only use `workflow_call`. Another important fact is that all inputs need to be passed using inputs (variables). In addition to inputs one can pass secrets when needed.

- you cannot use `github_token` as secret variable as it is reserved variable name

### Outputs

Reusable workflow can produce output and provide it back to workflow it uses.

These need to be defined at the level of job AND in workflow_call next to inputs and secrets, otherwise it will not work. I first made error defining outputs only at level of jobs
