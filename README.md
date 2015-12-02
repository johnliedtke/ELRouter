# Maynard

THGRouter.framework. A **work in progress** of a URL router for UIKit.

## Requirements

Maynard depends on [`THGFoundation.framework`](https://github.com/TheHolyGrail/Excalibur).

## Installation

Install by adding `THGRouter.xcodeproj` to your project and configuring your target to link `THGRouter.framework`.

## Usage


### Static Routes

Use static routes to manage URL routing with a `UITabBarController`.

```
// configure router to use UITabBarController for static navigation
let router = Router.sharedInstance
router.staticNavigator = UITabBarController(nibName: nil, bundle: nil)

// register routes for opening tabs
router.register(Route("home", type: .Static) { variable in
    let vc = HomeTabViewController(nibName: nil, bundle: nil)
    return UINavigationController(rootViewController: vc)
})

router.register(Route("more", type: .Static) { variable in
    let vc = MoreTabViewController(nibName: nil, bundle: nil)
    return UINavigationController(rootViewController: vc)
})

// evaluate a matching URL
let url = NSURL(string: "myapp://more")
router.evaluateURL(url)
```

## Contributions

We appreciate your contributions to all of our projects and look forward to interacting with you via Pull Requests, the issue tracker, via Twitter, etc.  We're happy to help you, and to have you help us.  We'll strive to answer every PR and issue and be very transparent in what we do.

When contributing code, please refer to our style guide [Dennis](https://github.com/TheHolyGrail/Dennis).

## License

The MIT License (MIT)

Copyright (c) 2015 Walmart, TheHolyGrail, and other Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
[]
