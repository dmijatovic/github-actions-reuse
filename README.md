# Github reusable actions

More complex experiments with github actions:

- reusable workflows
- passing variables between steps

## Reusable workflows

Official documentation can be [found here](https://docs.github.com/en/actions/using-workflows/reusing-workflows)

Usefull video is [thisone](https://www.youtube.com/watch?v=lRypYtmbKMs)

### Summary

For reusable workflow the action type should be `workflow_call`. You can use other triggers but then it might happend to trigger reusable action more than once. Therefore my conclusion is to create "pure" reusable actions that only use `workflow_call`. Another important fact is that all inputs need to be passed using inputs (variables). In addition to inputs one can pass secrets when needed.
