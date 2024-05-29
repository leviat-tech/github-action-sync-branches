# github-action-sync-branches

This action is to be used with repositories which contain `dev`, `main`, and `prod` branches which each deploy to their respective environment. The following table describes the event trigger and the resulting action:

| Event                                            | Action                                                              |
|--------------------------------------------------|---------------------------------------------------------------------|
| Push to `dev`                                    | PR from `dev` to `main` will be created entitled Deploy to Staging  |
| Push to `main` (i.e. merge Deploy to Staging PR) | PR from `main` to `prod` will be created entitled "Prepare Release" |
| Push to `prod` (i.e. merge Prepare Release PR)   | Release PR to `prod` will be created using `release-please`         |


