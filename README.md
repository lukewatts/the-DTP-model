The DTP (Development Testing Production) Model
=============

This is a simple workflow / model for Development, Testing and Production (D.T.P) phases of web applications.

### README

## DEVELOPMENT Branch (aka DEV Branch)
* Work should not be done directly on a development branch. Branches should be created for any work to be carried out and then merged into development. The development branch should be the most "stable" untainted version of this phase. In an Agile workflow this branch should only be updated at the end of a successful sprint, and should always be the closest to the testing phase.
* A directory should be created for excess files and assets. This should be clearly identifiable by placing a special character (such as an underscore) before it and keeping it in the projects root (e.g. _assets or _unused_assets). Files should NEVER be deleted from this folder while in the development phase, including branches created off of the main development branch.
* All files should be kept whenever possible! Extra files or unused files should simply be moved to the unused assets folder incase they are needed again.
* If a file is no longer being called from a page move it to _assets.
* Images should NOT be optimized. Optimization should be left for testing and production branches.
* PHP Errors should be turned on to the full possible.
* Database debugging features should be turned on.
* Strict mode should be enabled everywhere possible in PHP, JS, and MySQL.
* CDNs for scripts should NOT be used here. Development (Non-minified) releases of scripts should be used wherever possible.
* Only once the development branch is deemed in a major or relatively stable version should changes should be merged with the TESTING branch.

## TESTING Branch (aka BETA Branch)
* Work should not be done directly on a testing branch. Branches should be created for any work to be carried out and then merged back into testing. The testing branch should be the most "stable" untainted version of this phase. In an Agile workflow this branch should only be updated at the end of a successful sprint, and should always be the closest to the production phase.
* This branch should be tested on a LIVE testing server NOT a local (localhost) setup.
* Files and performance should be benchmarked and logged in concatenated vs non-concatenated and minified vs non-minified.
* All images should be optimized using a "Save for web..." or optimize for web. Images should be optimized gradually and tested and logged for best highest performance / quality ratios.
* CDNs for scrips and frameworks should be used in the main testing branch, but not strictly in branches created from this branch.
* Caching should be enabled here.
* Once any modifications are finished and the testing branch is deemed stable and safe for a live production environment only then should it be moved to production.

## PRODUCTION Branch (aka STABLE)
* No work should be carried out on this branch in any way!
* No branches should ever be created off of this branch. Any new features, bug fixes, patches or edits should be done in Development and only then moved to testing, and from there to development.
* All logfiles, temp files, temp folder, unused or unnecessary files and folders should be deleted from the filesystem once merged from the testing branch.
* All possible scripts should be concatenated and minified (JS, CSS etc).
* PHP Errors should be turned off.
* Database debugging features should be turned off.
* MySQL, PHP and Javascript should be set to "Forgiving Modes" where possible.

## NOTES
* This model only works if task are carried out in small, focused chunks. Branches should reflect these tasks with meaningful names and frequent commits. 
* In each phase the main branch should be complete or near complete in regards to the goal(s) of that phase. This ensures a constant "close to shipping model" with no downtime or risk while features are being developed and tested, issues or bugs are being fixed. Basically, the main branch (Development, Testing) needed to be sent to the next phase it should always be ready for this purpose. Likwise the Production model should always be in a stable working state for the end user / purpose.
* Production is generally the best suited to be the master branch. The initial sprint(s) should be carried out with the goal of creating a production ready master branch as soon as possible. However, the default branch should be set to Development as this will be the most worked on.