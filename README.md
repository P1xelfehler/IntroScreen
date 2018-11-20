# IntroScreen

[![CI Status](https://img.shields.io/travis/P1xelfehler/IntroScreen.svg?style=flat)](https://travis-ci.org/P1xelfehler/IntroScreen)
[![Version](https://img.shields.io/cocoapods/v/IntroScreen.svg?style=flat)](https://cocoapods.org/pods/IntroScreen)
[![License](https://img.shields.io/cocoapods/l/IntroScreen.svg?style=flat)](https://cocoapods.org/pods/IntroScreen)
[![Platform](https://img.shields.io/cocoapods/p/IntroScreen.svg?style=flat)](https://cocoapods.org/pods/IntroScreen)

A beautiful intro screen for iOS written in Swift.

![](IntroScreen.gif)

## How to use:

1. Add a ViewController to your storyboard & set IntroViewController as the class.

2. Add a segue to this ViewController

3. Set the introDataSource to the IntroViewController in prepareForSegue()

3. Configure the ViewController in your data source like this:

```swift
var numberOfPages: Int {
  return 3
}

// Return true, if you want to fade out the last page colour into black.
var fadeOutLastPage: Bool {
  return false
}

func viewController(at index: Int) -> IntroPageViewController? {
  switch index {
    case 0:
      return DefaultIntroPageViewController.getInstance(
            index: index,
                hue: 30/360,
                title: "First page",
                subtitle: "This is the first page.",
                image: UIImage(named: "first")
            )
    case 1:
      return DefaultIntroPageViewController.getInstance(
                index: index,
                hue: 60/360,
                title: "Second page",
                subtitle: "This is the second page.",
                image: UIImage(named: "second")
            )
    case 2:
      return DefaultIntroPageViewController.getInstance(
                index: index,
                hue: 90/360,
                title: "Third page",
                subtitle: "This is the third page.",
                image: UIImage(named: "third")
            )
    default:
      return nil
  }
}
```

Of course you can also use a custom view controller for the pages. Just extend IntroPageViewController. But you have to give it a clear background, so that the colours are visible.

## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Installation

IntroScreen is available through [CocoaPods](https://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod 'IntroScreen'
```

## Author

P1xelfehler, norman.laudien1996@gmail.com

## License

IntroScreen is available under the MIT license. See the LICENSE file for more info.
