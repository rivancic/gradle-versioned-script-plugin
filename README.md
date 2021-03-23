# Gradle Versioned Remote Script Plugin Example

This source code is part of [Gradle build tool example projects](https://github.com/rivancic/gradle).

It contains Gradle script plugin that will be used in the lecture explaining script plugins.

Why it is named versioned remote script plugin?

- **Script plugin**: First it's a script plugin that can be applied in build.gradle script. It contains files tasks that you should be 
familiar with since the tasks lecture.
- **Remote**: It's meant to be accessed over network to remotely located script plugin here in Github code repository. The 
repository is publicly available, everyone has access to it so everyone can include script in their own gradle script.
- **Versioned**: One way to version the process of evolving this plugin is to use handy git tags. With git tags we can add
changes to the remote script plugin. If script plugin is referenced with the tag name then existing usage of this plugin 
  is not affected with possible breaking changes in the future.
  
## Remote script plugin access

To apply this script plugin in other projects you have to use the following apply command in 
your gradle script file:

`apply from: 'https://github.com/rivancic/gradle-versioned-script-plugin/blob/master/scriptPlugin.gradle''`

As this is versioned file in git repository you will always fetch the latest version of the script.
Maybe the new version of the script contains changes that require different configuration, has behaviour that
you don't expect in your build.

## Versioned remote script plugin access

To mitigate risks mentioned above you can use git tags, to mark different versions of the file.
When applying remote script plugin in your Gradle build script you can refer to specific version of
a script plugin.

`apply from: https://github.com/rivancic/gradle-versioned-script-plugin/blob/v1.0/scriptPlugin.gradle`

Notice tag **v1.0** name following after a **blob/** path in the URL. Now you can expect that functionality of scriptPlugin.gradle
will never change. With using versions you can guarantee stability to your build process.