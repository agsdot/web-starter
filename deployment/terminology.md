---
layout: default
title: Terminology
---

With both Grunt and Capistrano there's a fair amount of specific
terminology used by the tool. While it's beyond the scope of this
documentation to talk through all of it, some of it will come up in the
documentation for configuration options.

### Grunt terms

task
:   Each Grunt plugin exposes one or more tasks that take options and
    are triggered from the grunt CLI, e.g. compass. Tasks can be created
    via the grunt.registerTask function that will run composite tasks,
    and the "default" task is required to be defined this way.

target
:   More specific options within a task, e.g. compass:dev. If a task is
    run then all targets within that task are run or they can be
    triggered specifically.

### Capistrano terms

stage
:   Defines what part of the software lifecycle you are deploying. In
    the Web Starter Kit there are three that are defined: dev, stage
    and production. It's assumed that each stage may live on different
    hosts with different file systems, etc. but the majority of the
    actions to deploy the application will remain the same. Each stage
    corresponds to a file in the config/deploy directory and defines
    variables that are used by the Rake tasks used by Capistrano. The
    Web Starter Kit also makes some assumptions about the naming of
    environment specific configuration files, things like .htaccess,
    robots.txt and settings.php for Drupal, assuming there are files in
    the repository that are namespaced by the stage, e.g.
    settings.dev.php.

role
:   Defines categories of hosts where certain tasks are executed. For
    example, when deploying a Drupal application to multiple servers
    it's unlikely you will need to run update hooks or apply stored
    configuration on each application server. So there may be multiple
    application servers that need to host the code, but only one db
    server that needs to apply the updates. Each stage defines the roles
    and hosts necessary for deployment.

{% include menus/deployment.md %}