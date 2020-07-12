# riotkit-harbor-snippet-cooperative
Snippet repository for RiotKit's Harbor - docker-compose YAML templates for services (applications, databases, etc.)

## Rules

1. Snippets are versioned, but does not offer an upgrade from version to version. We do not want a complexity, those are snippets, not packages
2. Snippets are providing containers, networks and volumes
3. The containers should be placed always in main network to reduce complexity for end user
4. The snippets does not need to be parametrized for each case, if something is complex, then let's create a second snippet with a different use-case, different workflow
5. Dependencies such as database connection should be customized with environment variables
6. Dependencies on other snippets should be placed in README.md of given snippet. Snippets are not packages - we do not support dependencies, the DevOps is an aware person that uses example code for faster development from ready-to-use blocks of code
7. Collisions in files should be avoided, but it may happen. It's not a package manager. The DevOps should be aware and track changes in GIT repository - Harbor operates on a GIT repository
8. The `harbor :coop:install` is a tool for human, not for automation, it considers interactive questions to the person who installs a snippet

## Snippet structure

```bash

# files to copy to main directory of the project, can contain subdirectories and files for a recursive copy
files/

# optional installer customizations
.rkd/makefile.yaml
```

## Snippet installer customizations

- `:snippet:copy` allows to overwrite a task that copies files of a snippet to the project root directory
- `:snippet:prepare` allows to prepare files in the snippet directory eg. render jinja2 files basing on questions answered by the user

