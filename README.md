# mps-dependency-module

## Motivation
In MPS we use languages, modules, models, java stubs from jar files as dependencies and others in a model.
Although we can write our own plugins, we might need plugins from other vendors.
We intrinsically need to have the knowledge, which plugins need to be preinstalled in our MPS, or our User Config Folder to open a project.
This plugin for MPS is going to implement functionality to improve the handling of dependencies of a project.

## The situation as is
If the plugin is hosted on a plugin repository, this might be helpful to find and install them „on the fly“ with need to restart the IDE after downloading and installation.
And voila the project should not look that ugly anymore :)

## The situation with this plugin
Based on information stored in the project the dependency will be served to the project.

## The presentation of the dependency
The dependency modules will be presented as a virtual folder in the tree view.
Each dependency module can have different aspects to unfold underneath:
  * a language might unfold the aspects like in the modules virtual folder
  * a maven artifact dependency might unfold java-sources, java-docs, jar-files, other attachments to the artifact, and transitive dependencies... excludes etc.
  * a dependency module can decide what to present.
  
## The dependency module as dependency
The dependency module can then be used in other modules as dependency.
It will provide the languages, modules, models as if they were preinstalled.

## Enabling automatic build?
For the time being in MPS Projects we create a build script for generating the sources, compilation, packaging and naming of the artifacts. The build should be best supported by the dependency modules.
My favorite would be just scriptless build by modeling the artifact outcome and its dependencies as layed out in the project will be used to fulfill the whole build and packaging.
