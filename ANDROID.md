# Guidelines for Android Projects

## Introduction

These are meant to help keep the code uniformly organized and standardized in such a way as to reduce as much as possible the time needed for new developers to get to be productive on different projects.
The following are lessons learned from having worked on different Android projects. They are not written in stone, but keep in mind that being consistent and not reinventing the wheel with each project will make the lives of future developers that need to take on your projects simpler and also lead to faster development times of new features or bug fixes. Feel free to add your own.

## Code Conventions
Android projects are Java projects, so they must follow the well-known code conventions for the Java programming languages. These are easily available online so look for them and apply them to the projects.

## Project Estimation
When asked to work on a new estimate for a potential project for a client, keep in mind that, despite what you may hear, there's a good chance your estimates will get converted into deadlines, so really take your time to work on them. If given the designs or wireframes, look at them carefully..
- What are the UI widgets you need to use to construct those designs?
- Are they standard or customized?
- How much customization do they need?
- Have you worked with them before?
- Are they available in all API levels requests by the client?
- While looking at the designs, also try to make a mental map of how the overall communication of the app will be.
- How will the user transition from one view to another?
- Are there animations involved? Will certain views need to be updated automatically?

Make sure you take those items into account and include them into your estimates. If you have a feeling a certain design will not be easy to accomplish, create a separate item for them in the estimates document. Estimating designs is an important part of the estimation process, but it is not the only one. You also need to take into consideration other factors such as the backing data model, backwards compatibility with older Android API levels, integration with social networks, etc...
- Will the app need to keep a local cache of the data?
- How many API calls do you imagine the app to have?
- How will you communicate with the backend?
- Etc, etc, you get the point.

If you have any doubts, questions, comments, heads-up, suggestions etc, write them down in the estimates document and keep in mind that it's better to under-promise and over-deliver then to over-promise and under-deliver.

## Tips
#### Use Android Studio and Gradle
With Gradle, it's much easier to handle project dependencies, configure different build flavors (production, staging, etc), and when combined with Android Studio, it's also easier for new developers to setup their initial development environment. So, stay away from Eclipse unless you absolutely have to :)

#### Custom Android data structures
Use specialised data structures such as SparseArray, SparseBooleanArray, and LongSparseArray instead of generic ones like HashMap. For most tasks, these are more memory efficient and the interface they expose is the same as the generic data structures, so the benefits are transparent.

#### Avoid making deep hierarchies in your views
When creating layouts, keep in mind that these are simple XML files that, when inflated, need to be parsed recursively by Android, so the deeper the hierarchy of your views, the more processing will be needed. If you notice that the hierarchy of your views are too deep, try to re-thing how you're constructing your UI. Can you simplify your layout by transforming LinearLayouts into RelativeLayouts?

#### Use Fragments
Fragments are a great way not only to representa reusable parts of your UI, but also to encapsulate behaviour. Try to envision your UIs using fragments instead of Activities. Using this schema, you can retain all of the UI and logic inside fragments and use Activities only as managers of those fragments. Keep in mind that, just like Activities, Fragments manage their own lifecycle.

###### Packages architecture
Try to organize and group classes together inside packages that share a common intent. A new developer should be able to easily guess where a certain class is by looking at the package names. For example, here are some common packages used in some of our projects:

> com.inaka (package name)
- network
- models
- utils
- activities
- fragments
- adapters

#### Libraries
Don't hesitate to use third-party libraries for common tasks. If you're undecided between different libraries, take a look at their Github repo. How ofter do they get updated? Which one has the most active community? How often are issues opened and resolved? Who's behind those libraries? Companies or individuals? When using a new library, you will probably have a lot of questions at first, so make sure you don't shoot yourself in the foot by choosing an outdated library no one uses anymore. As a sidenote, remember that your Android projects has a 65k method limitation, and each external library you add to your project will contribute to this number, so make sure the benefits of the library outweighs the drawbacks.

Here are a few libraries we like and have worked with in the past:
- Picasso for image loading and caching
- Universal-Image-loader: use this only if you need to cache images on disk, if not, pick Picasso
- Retrofit for defining you API calls and implementing a Rest Client
- OkHTTP for efficient HTTP requests
- Otto for event-based inner app communication
- Butterknife to reduce amount of boilerplate code between java and xml files
- Parceler to reduce boilerplate code needed to make your POJOs implement Parcelable interface

#### Naming conventions
To maintain consistency, make sure you follow the same naming conventions throughout your code. This applies to java source files as well as resources, for example:
- Fragments: fragment_name.xml
- Activities: activity_name.xml
- Dialogs: dialog_name.xml
- Views: view_name.xml
- Menus: menu_name.xml
- Animations: animation_name.xml
- Button drawables: button_name.xml
- You get the point. Whatever your naming convention, make sure you don't change it halfway.

#### Use styles
When starting a new project, take a moment to review the designs and identify reusable components instead of jumping right into coding. Identify components such as titles, subtitles, font sizes, etc and group the ones together that share the same parameters. Create styles for them and make sure you use them in all of the xml layout files. Never hard code values such as background and foreground colours, font sizes, font styles, heights, etc into each UI widget. Instead, define each widget's basic required fields (Eg. id, width, height) and have their other attributes loaded via a style.

- Use a palette: This is similar to the point above. Instead of hard coding colours into the xml files, make use of the colors.xml file and add all of the required colours used throughout the app in there. Don't try to guess which colours they are by looking at the design documents or using an onscreen color picker. Instead, ask the client for the specific color palette. A useful tip is to name your colours by their actual color names variants, for example "green", "light_green", "blue", etc instead of things such as "signin_button_color", "logout_button_color". By using the second approach, you will quickly find yourself in a mess of duplicate hex color values.

- Dimensions: Same thing goes for dimensions such as UI widget heights, spacing, etc. Make sure they all go into the dimens.xml file and are not hard-coded into the XML files.

- Strings: Even if the app will not need to be translated into other languages, always use the strings.xml file to store any text used throughout the app. This helps keeping the app standardized and will also speed up any future text-related modifications needed.

#### Build flavors
Very often projects need different values for different scenarios. For example, we might need one build to point to a staging backend and another one to a production backend. Also, we might want the staging build to display some sort of UI element indicating this, or maybe have an increased level of logging compared to the production builds, etc. For these scenarios, you can configure Gradle to automatically make the necessary modifications to your codebase and resources to reflect your different flavors. You'll find that it saves a lot of time to implement this from the start, instead of having to manually change those values everytime someone asks you for a specific type of build. Documentation on this is freely available online, but you can start by reading our Inaka blog post about it ["here"][effective-code-review].

#### Google Play Services
You'll use this library if you need to implement things such as push notifications, google analytics, Play Services, etc. In the past, this meant adding a huge monolithic library to your project that consume a huge chunk of your 65k method limit, but not anymore. The good guys at Google decided to break these into individual libraries, so now we can pick and choose which ones we want. As a result, we have slightly faster build times, and less unused code. Simply add the individual libraries to your build.gradle file like so:
>
- compile 'com.google.android.gms:play-services-base:[check-for-latest-version]'
- compile 'com.google.android.gms:play-services-ads:[check-for-latest-version]'
- compile 'com.google.android.gms:play-services-fitness:[check-for-latest-version]'
- ...

[flavors]: http://inaka.net/blog/2014/12/22/create-separate-production-and-staging-builds-in-android/
