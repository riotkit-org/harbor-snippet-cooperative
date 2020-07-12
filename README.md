# riotkit-harbor-snippet-cooperative
Snippet repository for RiotKit's Harbor - docker-compose YAML templates for services (applications, databases, etc.)

## Rules

1. Snippets are versioned, but does not offer a upgrade from version to version. We do not want a complexity, those are snippets, not packages
2. Snippets are providing containers, networks and volumes
3. The containers should be placed always in main network to reduce complexity for end user
4. The snippets does not need to be parametrized for each case, if something is complex, then let's create a second snippet with a different use-case, different workflow
5. Dependencies such as database connection should be customized with environment variables
6. Dependencies on other snippets should be placed in README.md of given snippet. Snippets are not packages - we do not support dependencies, the DevOps is an aware person that uses example code for faster development from ready-to-use blocks of code
