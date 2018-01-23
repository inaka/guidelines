# Guidelines for iOS Projects

## Introduction
These guidelines are meant to help keep the code uniformly organized and standardized, in such a way, that we can reduce as much as possible the time needed for new developers to get to be productive on different projects. The following lines are lessons learned from having worked on different iOS projects. They are not written in stone, but keep in mind that being consistent and not reinventing the wheel with each project will make the lives of future developers that need to take on your projects simpler, and also lead to faster development times of new features or bug fixes. Feel free to add your own.

> For specific language reference, check out our [Swift Guidelines](https://github.com/inaka/swift_guidelines/wiki).

***

## Project Estimation
When asked to work on a new estimate for a potential project for a client, take your time to work on them. If given the designs or wireframes, look at them carefully.
- What are the UI widgets you need to use to construct those designs?
- Are they standard or customized?
- How much customization do they need?
- Have you worked with them before?
- Are they available in all API levels requested by the client?
- While looking at the designs, also try to make a mental map of how the overall communication of the app will be.
- How will the user transition from one view to another?
- Are there animations involved? Will certain views need to be updated automatically?

Make sure you take those items into account and include them into your estimates. If you have a feeling a certain design will not be easy to accomplish, create a separate item for them in the estimates document. Estimating designs is an important part of the estimation process, but it is not the only one. You also need to take into consideration other factors such as the backing data model, backwards compatibility with older iOS API levels, integration with social networks, etc...
- Will the app need to keep a local cache of the data?
- How many API calls do you imagine the app to have?
- How will you communicate with the backend?
- Etc., etc., you get the point.

If you have any doubts, questions, comments, heads-up, suggestions etc., write them down in the estimates document and keep in mind that it's better to under-promise and over-deliver than to over-promise and under-deliver.

***

## Code Conventions
As for writing Objective-C code, we have created our own **[Objective-C Coding Standards & Guidelines](https://github.com/inaka/ios_guidelines)** repo, where we have gathered many concepts from experience and arranged them into two main sections:
* [Rules](https://github.com/inaka/ios_guidelines/blob/master/rules.md) *(which must be strictly followed)*
* [Suggestions](https://github.com/inaka/ios_guidelines/blob/master/suggestions.md) *(just good ideas to be considered when writing code, which are not mandatory to follow though highly suggested)*.

***

## General Conventions for iOS Projects

***

#### Standards
These are the technologies that we expect every iOS project to adopt:
* [Cocoapods](http://cocoapods.org/) for managing dependencies.
* [Storyboards](https://developer.apple.com/library/ios/recipes/xcode_help-IB_storyboard/_index.html) for building the application UI.
  * We suggest:
     * Separated storyboards for different flows of the app *(e.g. LoginStoryboard, MainStoryboard, SettingsStoryboard, CreatePostStoryboard, etc)*.
     * XIB files only when necessary *(e.g. separated views that don't fit in any storyboard)*.
* [Auto Layout](https://developer.apple.com/library/ios/documentation/UserExperience/Conceptual/AutolayoutPG/Introduction/Introduction.html) for setting up UI elements arrangement in app view controllers.
* [AFNetworking](https://github.com/AFNetworking/AFNetworking) as default library for networking.
* [jayme](https://github.com/inaka/jayme) as default RESTful API abstraction layer for server interconnection.

***

#### File Organization
This is the way we expect iOS project files to be organized:

* **Logically** (from Xcode), files separated in **groups** by **kind** *(what they are for)* rather than by navigation or functionality related to the app *(where they would fit in the app)*, so as:

    > * Project
    >   * **AppName**
    >     * Assets
    >     * Storyboards
    >     * Model
    >     * Controller
    >     * View
    >       * Views
    >       * Cells
    >     * Remote
    >     * Helpers
    >     * Categories
    >     * Supporting Files
    >     * XIBs
    >   * AppNameTests
    >   * Frameworks
    >   * Products
    > * Pods

* **Physically** (from Finder), files separated in **folders** as following:

    > * project-github-name
    >   * *README.md*
    >   * [build_support](#build-support)
    >   * AppName
    >     * *Project.xcodeproj*
    >     * *Project.xcworkspace*
    >     * *Podfile*
    >     * *Podfile.lock*
    >     * **AppName**
    >       * Assets
    >       * Storyboards
    >       * Model
    >       * ...
    >     * AppNameTests
    >     * Pods

* Pay special attention to **AppName** folder and group (both marked in bold), because **AppName** is the folder where files that are logically located inside the **AppName** Xcode logic group must be placed into.

* In addition, there must be a folder per each subgroup inside **AppName** group, so that every single file into the *Model* subgroup (for example) belongs with a folder named *Model* inside the **AppName** folder.

* Nonetheless, no more nesting levels are required as for correspondency between physical folders and logical groups. For instance: If you have a *User* subgroup inside the *Model* group, there must be no physical folder to put *User-related* files into; they would just go inside the *Model* folder.

***

#### Asset Organization
* Images must be in **.png** format and their names must match the following conditions:
  * Camel case, starting with uppercase. Examples:
    * *SeatIcon.png*
    * *NavigationBarMenuIcon.png*
  * For retina and high quality versions, include "@2x" or "@3x" suffix accordingly before filename extension. Examples:
    * *SeatIcon@2x.png*
    * *SeatIcon@3x.png*
    * *NavigationBarMenuIcon@2x.png*
    * *NavigationBarMenuIcon@3x.png*
  * For different button state images, append a single dash "-" and the state name (ideally matching apple's conventions for naming states) as a suffix, preceding the filename extension and the image quality suffix, if present. Examples:
    * *SeatButtonBackground-Highlighted@2x.png*
    * *SeatButtonBackground-Selected@2x.png*
    * *SeatButtonBackground-Disabled@2x.png*
    * *SeatButtonBackground-Default@2x.png*
  * And remember, always be consistent with naming. We don't define strict rules as for naming assets, but you should consider naming it according to a logical sense.
* Every image must be inside **Images.xcassets** folder. An acceptable exception is creating different *.xcassets* folders for grouping assets that were given different categories. What's not acceptable is to have images that are not inside any *.xcassets* folder.
* Use default naming for **application icon** and **splash image**, meaning that all you need to do is drag and drop those images in their default containers within the **Images.xcassets** folder in Xcode.

***

#### Build Support
* Every iOS project must include a *build_support* folder located at the root level, whose content must include every file that is generated in order to support building and distrubution processes and also push notification support related files. Typically it involves: **.mobileprovision** files, **.p12** files, **.pem** files and **.cer** files.
* Those files must be properly named as to identify the environment they work with (*development* vs. *distribution*).
* That folder must always be up to date, like all the files involved each time a new certificate is generated, a new device is added to a provisioning profile or any other updating process occurs.
* There are two purposes for having such a folder and maintaining it updated. The first one is that it helps other developers to avoid code signing issues and lowering, in consequence, involved time spent to setup app's distribution process, since they will always have everything they need inside a folder that's included in the project's git repo. The second purpose is that these files are usually required to be set on Jenkins in order for it to perform continuous integration builds.

***

#### Product Versioning
Every iOS application must be versioned according to the following structure:
> `X.Y.Z`

Being `X`, `Y` and `Z` all **integer numbers**, where:
> * `X` represents the **version number**.
> * `Y` represents the **sub-version number**.
> * `Z` represents the **build number**.

And having in mind that:
> * `X` should change whenever the application suffers **big changes** so that it can't be considered compatible anymore with its previous versions or it's too different that it could be considered a different app.
> * `Y` should change whenever a **new feature** is added, but it's not too big as to consider the app has suffered any breakthrough changes.
> * `Z` should change for **bug fixes, crash fixes, little UI improvements** or other things that don't add new functionality, but enhance the user experience.

For instance, this is what the full version number increasing should be like, according to their comments aside:
> * `1.0.0` *Initial version.*
> * `1.0.1` *Fixed minor bugs.*
> * `1.0.2` *Fixed UI bugs.*
> * `1.1.0` *Added forgot password functionality.*
> * `1.1.1` *Enhanced UI buttons response.*
> * `1.2.0` *Added possibility to choose among different color skins.*
> * `2.0.0` *Complete new design. Added lots of new features.*

From Xcode's target settings, always use the **version number** field to specify `X` and `Y` and the **build number** field to specify `Z`. For instance, if the version number is `2.1.15` then you should be using Xcode's fields the following way:

![Versioning in Xcode](https://github.com/inaka/inaka_corp/blob/master/source/assets/img/xcode-versioning-example.png)
