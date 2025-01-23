# RHDE-1: Building Red Hat Device Edge Images

This course teaches how to create Red Hat Device Edge images for edge devices and kiosk computers. It is the starting point of a larger learning journey which targets RHEL for Edge and MicroShift. As more courses are released, we'll update this page with links to them.

Sample applications and configuration files are in the [rhder-build-samples](https://github.com/RedHatQuickCourses/rhde-build-samples/tree/main) repository.

The course design docs are available to Red Hat employees only:

* [Initial course design](https://docs.google.com/document/d/1WloibD7XzA8SRunD5c1XktAzXAC_0D0ChAYddQzkgmI/edit?usp=sharing)

Figures on this course are designed using Google Slides, and the deck is available to Red Hat employees. Individual slides are exported to SVG files and cleaned using Inkscape. Those files are in the git repository.

* [Figures](https://docs.google.com/presentation/d/1tpZx28kQ2hITdSKmMf4ho7QsNuV0XygGI4ZOTPFj7nY/edit?usp=sharing)

Refer to the [Red Hat Quick Courses Contributor Guide](https://redhatquickcourses.github.io/welcome/1/guide/overview.html) for instructions about collaborating in this repository.

The first release of this borrows a virtual classroom environment from another course, see [here](https://docs.google.com/document/d/1WzCPaNG-IPubtlqYtvQlz6XHVVWtDZscWSBqwgLDzmo/edit?usp=sharing) notes about the progress on creating a classroom environment customized for the requirements of this and other RHDE courses. The current course release uses a ROLE classroom shared by all Red Hat Device Edge quick courses.

## Updates

The course was updated for RHEL 9.5 and tested on new ROLE classroom, which are shared by all Red Hat Device Edge quick courses and will be updated as required by future related courses: *HOL014: Red Hat Device Edge Quick Course Series*.

## Other Red Hat Device Edge Quick Courses

Currently, the Red Hat Device Edge learning journey includes:

* Building Red Hat Device Edge Images (this course)

* [Deploying MicroShift on Red Hat Device Edge](https://github.com/RedHatQuickCourses/rhde-microshift/)


## Experimentation with Antora

This course is trying new features of Antora and AsciiDoc (new for the Product Enablement Team, at least) so it requires some settings that are different from other Red Hat Training Quick Courses:

* On antora.yml, add asciidoc.attributes.experimental: true
* On antora-playbook.yml, add content.sources that point to the GitHub URL of the course samples repository
* On package.json, the watch.doc command requires the --fetch option

The first change supports using asciidoc macros such as kbd: The other two changes support using code sample files directly in listings inside adoc files, so we don't need to cut-and-paste.

This course also uses asciidoc attributes for information that changes everytime you run a command, such as ostree commit IDs and image builder compose UUIDs, to ensure they are consistent in commands and outputs, and the ouputs in labs are useful to learners as a reference that "this is what I should see if all is fine". We're using site-level attributes (in antora.yml) for attributes that must keep their value between different labs, such as commit IDs, and page-level attributes (in each *-lab.adoc file) for attributes that shouldn't ne nedded in multiple labs, such as compose UUIDs.

Also notable experiments in this course:

* Using collapsible sections for quiz answer feedback
* Using xrefs to reference prerequisites that come from previous labs
* Using generic names for virtual machines, to reinforce their roles and help adapting the contents for different environments
