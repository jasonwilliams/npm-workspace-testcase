# NPM Test Case

NPM: v8.3.0
Node: v17.3.0
Yarn: 1.22.5

NPM is not respecting workspaces when installing inside a sub-package (or workspace as NPM calls them). This is leading to unpredictable behaviour and bugs.

The preferred solution would be to follow Yarn's approach in detecting a package is in a workspace and update the top level package-lock instead of creating a new one.

## NPM

- run `npm i` inside of `project-a` folder

### Outcome

package-lock is generated inside of `project-a` folder (including a node_modules)

### Expected

Top-level package-lock is updated along with node_modules at the top level (where appropriate)

## Yarn

- run `npm i` inside of `project-a` folder

### Outcome

Top-level package-lock is updated along with node_modules at the top level (where appropriate)
