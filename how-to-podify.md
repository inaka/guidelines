## How to Podify an iOS repo

####What does *podify* mean?

We've invented the verb "to *podify*" to mean "to make an iOS repository be available in [cocoapods](http://cocoapods.org/)".

-

#### What are the steps to accomplish that?

1. Create the podspec file in your root folder (`/ExampleProject.podspec`) and fill it by using [this template]([https://github.com/inaka/SelectionManager/blob/master/SelectionManager.podspec](https://github.com/inaka/SelectionManager/blob/master/SelectionManager.podspec)) as a model.
2. Commit, Pull Request, and, once merged into master branch, create a git tag with the version number you specified in the `podspec` file.
3. Run in terminal (using `--verbose` if you get errors): 
   1. `pod lib lint`, which checks your project locally
   2. `pod spec lint`, which checks remotely against git
4. Once passed, [trunk]([https://guides.cocoapods.org/making/getting-setup-with-trunk](https://guides.cocoapods.org/making/getting-setup-with-trunk)), which basically is running:
   1. `pod trunk me`
      - if no session registered: 
        - `pod trunk register your@emailaddress.com 'Your Name' --description='your computer description'`
        - Verify email link
   2. `pod trunk push`

That's it!

- **Note:** It will take some time for your pod to be available in [cocoapods](http://cocoapods.org/) search page.