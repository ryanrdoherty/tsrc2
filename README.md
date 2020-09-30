# tsrc2
Repository containing the tsrc 2.x multi-repository manifest

## Examples

### Check out all projects in a given group (e.g. clinepi site, data loading, all site types)
```
tsrc init git@github.com:VEuPathDB/tsrc.git --group baseProjects
```
### Update all projects (or in a group) at the same time
```
tsrc sync
```
(this can be run within any project, to update all projects)

### View sync merge consequences (to a branch) for a group of projects without merging
```
tsrc foreach -- git diff master..api-build-44 
```
Or (many options with git diff):
```
tsrc foreach -- git diff master..api-build-44 --name-status
tsrc foreach -- git diff master..api-build-44 --stat
```
### Sync merge a group of projects without committing
```
tsrc foreach -- git merge master --no-commit
```
### Commit a sync merge for a group of projects all at once
```
tsrc foreach -- git merge master
```
(if projects are checked out on a branch, this would merge master into branch)

### Reintegration merge (e.g. back to trunk) for a group of projects
```
tsrc foreach -- git merge api-build-44
```
### Branch a group of projects all at once
```
tsrc foreach -- git checkout -b mynewbranch
```
### Tag a group of projects all at once
```
tsrc foreach -- git tag mytag
```
### Switch a group of projects from trunk to branch or back (believe this is just a git feature)
```
tsrc foreach -- git checkout branchname
```
