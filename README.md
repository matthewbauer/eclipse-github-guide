Group collaboration with Eclipse
================================

Requirements
------------
You'll need the following for this guide:

* Eclipse IDE for Java Developers
* GitHub app

Initial Project Setup
---------------------
* Open Up the Github app
  * Create repository
    * Name is your repository name
* Open Up Eclipse
  * File->New->Java Project (if not already there)
  * Right click on the project
    * Team->Share Project->Git
    * Create->Browse
      * Navigate to your GitHub directory (Should be called "GitHub")
      * Select your GitHub repository
      * Finish
    * Finish
  * Click Window->Show View->Navigator
    * Open the .gitignore file in your project and add the following:
```gitignore
.DS_Store
.classpath
.metadata
.recommenders
bin
target
*.class
*.zip
*.jar
*.log
```
  * Right click on the project
    * Configure->Convert to Maven Project
    * Use defaults
    * Finish
  * Right click on the project
    * Properties
      * Java Code Style->Enable project specific settings
      * Java Code Style->Clean Up->Enable project specific settings
      * Java Code Style->Code Template->Enable project specific settings
      * Java Code Style->Formatter->Enable project specific settings
      * Java Code Style->Organize Imports->Enable project specific settings
      * Java Compiler->Building->Enable project specific settings
      * Java Compiler->Javadoc->Enable project specific settings
      * Java Compiler->Task Tags->Enable project specific settings
      * Java Editor->Save Actions->Enable project specific settings
      * Task Repository->Enable project specific settings
      * Task Tags->Enable project specific settings
      * Validation->Enable project specific settings
      * Validation->XML Syntax Enable project specific settings
  * Right click on the project
    * Run as->Run Configurations
      * Right click on Maven Build and select New
      * Select New_configuration under Maven Build
      * Name will be "Get dependencies"
      * Browse Workspace->Ok
      * Goals: "dependency:resolve"
      * Select Common tab
        * Check "Shared file" and click browse
          * Under your project, select ".settings"
        * Check "Run" under display in favorites menu
      * Click "Apply"
      * Click "Close"
  * Right click on the project
    * Team->Commit
      Commit message: "Added project configurations"
      Make sure the author and committer are correct
      Select all of the files
      Commit
* Go back to GitHub
  * Click Publish
    * Push repository

Group Member Project Setup
--------------------------
* Open GitHub app
* Click the plus
  * Clone
    * Find your project
    * Clone
* Open Eclipse
  * File->Import->Maven->Local Maven Project->Existing local repository
    * Click add...
      * Browse
        * Locate you GitHub folder, select the project inside
        * Finish
    * Finish

Problems
--------
If someone in your team is having issues with their workspace, here are a few things to try:

* Project->Clean
* Run->Get dependencies
* !!! Team->Reset->Remote Tracking
  * Check "Hard"
  * Reset
  * This will get rid of any changes you have made since the last commit!
