# License

See the accompanying LICENSE file.

# About

The intent of these tools to create a Runtime CSS style SWF to be loaded into an Adobe Flex Application targeting a custom configuration in order to not build against runtime RSLs which is the default for the MXML compile tool from the Adobe Flex SDK.

If you use these tools in a custom project, you will need to modify the build.properties file to point to your proper Flex SDK and file resources.

# Usage

In previous version of the Flex SDK, the MXMLC tool could be used to compile a CSS file into a SWF to be used as a Runtime CSS document. Typically, that SWF file is generated using the following command:

> mxmlc MyStyle.css

The current default flex-config used by the MXMLC tool in Flex SDK 4 now links against several RSLs included in the SDK when generating a SWF. Unfortunately, these RSLs have no relevance when compiling a CSS file for Runtime. If the MXMLC tool used the default flex-config to compile a CSS file, when that Runtime CSS is loaded by an application, requests are made for those RSLs. Depending on your porject structure, that will often be an extrenuous call since the application has already loaded the RSLs needed.

The flex-runtime-css ANT build hopes to address this with a custom configuration file that removes the linkage of the default RSLs.