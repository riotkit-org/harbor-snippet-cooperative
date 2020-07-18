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
8. The `harbor :cooperative:install` is a tool for human, not for automation, it considers interactive questions to the person who installs a snippet

## Snippet structure

```bash

# files to copy to main directory of the project, can contain subdirectories and files for a recursive copy
files/

# optional installer customizations
.rkd/makefile.yaml
```

## Snippet installer customizations

- `:snippet:install` allows to overwrite a task that copies files of a snippet to the project root directory
- `:snippet:wizard` allows to create an interactive installation wizard for the end-user

From authors
------------

We are grassroot activists for social change, so we created this software while we were helping those fantastic initiatives:

- RiotKit (https://riotkit.org)
- International Workers Association (https://iwa-ait.org)
- Anarchistyczne FAQ (http://anarchizm.info) a translation of Anarchist FAQ (https://theanarchistlibrary.org/library/the-anarchist-faq-editorial-collective-an-anarchist-faq)
- Federacja Anarchistyczna (http://federacja-anarchistyczna.pl)
- Związek Syndykalistów Polski (https://zsp.net.pl) (Polish section of IWA-AIT)
- Komitet Obrony Praw Lokatorów (https://lokatorzy.info.pl)
- Solidarity Federation (https://solfed.org.uk)
- Priama Akcia (https://priamaakcia.sk)
