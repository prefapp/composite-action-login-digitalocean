# composite-action-login-digitalocean

This repository stores a [composite action](https://github.blog/changelog/2021-08-25-github-actions-reduce-duplication-with-action-composition/) used to set up digital ocean login in order to release a helm chart using helmfile.

You can use this composite action as a step in your workflow like:
```
 - id: aws-login
        if: ${{ steps.set-cloud-info.outputs.result == 'do' }}
        uses: prefapp/composite-action-login-digitalocean@v1
        with:
            cluster-name: ${{ env.CLUSTER_NAME }}
            auth-token: ${{ env.DO_TOKEN }}

```