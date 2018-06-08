# Vim Concourse Snippets

This is are snippets of the most common properties I use when creating concourse config YAML files. The snippets follow a specific syntax, which is:

`cc<property-name><specifics>`

where, 

- `cc`=concourse 
- `<property-name>`=name of a config property (eg job, task, etc.)
- `<specifics>`=somthing specific for a specific property (eg. git put declaration)

Example: `ccgit` creates:

```yaml
- name: name
  type: git
  source:
    uri: git@github.com:author/repo.git
    branch: master
    private_key: key
```

whereas `ccgitput` creates:

```yaml
- put: repo
  params: 
  repository: some-other-repo
```

## Requirements

- [SnipMate](https://github.com/garbas/vim-snipmate)

## Installation

### Pathogen

```bash
$ git clone https://github.com/JulzDiverse/vim-concourse-snippets ~/.vim/bundle/vim-concourse-snippets
```

### Usage/Commands

Open a `.yml` or `.yaml` file, in insert mode and type any of the following commands and hit \<tab\> (and continously hit \<tab\> to get to the next field):

```
Plan specific:
- ccjob
- cctask
- cctaskf (creates a task with a file reference)
- cctaskfile (creates a task file)
- ccget
- ccgit 

Resources specific:
- ccgit
- ccgitput
- cctimeinterval
- cctimerange
- ccdocker
- ccpool
- ccslackrt (slack resource type) 
- ccslack
- ccslackput
```

