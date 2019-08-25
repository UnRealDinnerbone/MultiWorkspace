# MultiWorkspace
Setup for a multi-mod workspace

Individual mods should be 'git cloned' inside subfolders of this project.
Modify settings.gradle as well as workspace/build.gradle for all your mods.
Inside the mods/build.gradle you should have the following construct to make sure the mods are still compilable standalone as well as inside the multi-project:

    if (project(':McJtyLib') != null) {
        compile project(':McJtyLib')
    } else {
        compile fg.deobf (project.dependencies.create("com.github.mcjty:mcjtylib:${mcjtylib_version}") {
            transitive = false
        })
    }

To setup this project, just open the root (empty) build.gradle as a project in IDEA. Run genIntellijRuns and select the one for the 'workspace' module


#Adding Mods

To add a mod the workspace but the dir in 
workspaces\


And once you import gradle into idea and do your setup pick "Forge-1.14.workspace.main".
