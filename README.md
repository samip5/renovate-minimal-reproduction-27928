## Renovate reproduction

Currently the replace string is incorrect, so that after Renovate tries to replace it, it results in it unable to find the version things anymore.
It should instead find the values correctly.

I would also prefer that the comment would be above it, but couldn't make that work.

Currently the following:
```
docker_image: ghcr.io/matrix-org/sliding-sync:v0.99.12  # renovate: datasource=docker depName=ghcr.io/matrix-org/sliding-sync
```

results in:
```
"deps": [
               {
                 "depName": "ghcr.io/matrix-org/sliding-sync",
                 "currentValue": "v0.99.12",
                 "datasource": "docker",
                 "versioning": "semver",
                 "replaceString": "\n      docker_image: ghcr.io/matrix-org/sliding-sync:v0.99.12 # renovate: datasource=docker depName=ghcr.io/matrix-org/sliding-sync\n",
                 "updates": [
                   {
                     "bucket": "patch",
                     "newVersion": "v0.99.15",
                     "newValue": "v0.99.15",
                     "newMajor": 0,
                     "newMinor": 99,
                     "updateType": "patch",
                     "branchName": "renovate/ghcr.io-matrix-org-sliding-sync-0.99.x"
                   }
                 ],
                 "packageName": "ghcr.io/matrix-org/sliding-sync",
                 "warnings": [],
                 "registryUrl": "https://ghcr.io",
                 "lookupName": "matrix-org/sliding-sync",
                 "currentVersion": "v0.99.12",
                 "isSingleVersion": true,
                 "fixedVersion": "v0.99.12"
               }
             ]
DEBUG: Starting search at index 555 (repository=ans/ansible, packageFile=playbooks/matrix.yml, branch=renovate/ghcr.io-matrix-org-sliding-sync-0.99.x)
       "depName": "ghcr.io/matrix-org/sliding-sync"
DEBUG: Found match at index 555 (repository=ans/ansible, packageFile=playbooks/matrix.yml, branch=renovate/ghcr.io-matrix-org-sliding-sync-0.99.x)
       "depName": "ghcr.io/matrix-org/sliding-sync"
DEBUG: Could not extract playbooks/matrix.yml (manager=regex) after autoreplace. Did the autoreplace make the file unparseable? (repository=ans/ansible, branch=renovate/ghcr.io-matrix-org-sliding-sync-0.99.x)
```
