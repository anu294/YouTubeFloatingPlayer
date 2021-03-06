# YouTubeFloatingPlayer

A Swift-based video player inspired by YouTube. Based on [SwiftYouTubeFloatingPlayer](https://github.com/hanappaula/SwiftYouTubeFloatingPlayer).

[![Version](https://img.shields.io/cocoapods/v/YouTubeFloatingPlayer.svg?style=flat)](http://cocoapods.org/pods/YouTubeFloatingPlayer)
[![License](https://img.shields.io/cocoapods/l/YouTubeFloatingPlayer.svg?style=flat)](http://cocoapods.org/pods/YouTubeFloatingPlayer)
[![Platform](https://img.shields.io/cocoapods/p/YouTubeFloatingPlayer.svg?style=flat)](http://cocoapods.org/pods/YouTubeFloatingPlayer)

## Features

- Interactive, drag to minimize, swipe to dismiss
- Supports TableView as well as any UIView for displaying video details

## Requirements

Currently YTFPlayer is only supported on applications supporting only portrait orientations. To implement the following code must be implemented in the AppDelegate :

```ruby
func application(application: UIApplication, supportedInterfaceOrientationsForWindow window: UIWindow?) -> UIInterfaceOrientationMask {
    return UIInterfaceOrientationMask.Portrait
}
```

## Dependencies

- [YouTube Helper](https://github.com/youtube/youtube-ios-player-helper)

## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Installation

[CocoaPods](http://cocoapods.org) is a dependency manager for Cocoa projects. You can install it with the following command:

```bash
$ gem install cocoapods
```

To integrate YouTubeFloatingPlayer into your Xcode project using CocoaPods, specify it in your `Podfile`:

```ruby
source 'https://github.com/CocoaPods/Specs.git'

platform :ios, '9.0'
use_frameworks!

target '<Your Target Name>' do
    pod 'YouTubeFloatingPlayer'
end
```

Then, run the following command:

```bash
$ pod install
```

## Usage

Use `YTFPlayer.initYTF()` method to initialise Player with desired properties.
Once initialised, use `YTFPlayer.showYTFView()` method with its parameter set to the desired ViewController.

```ruby
import YouTubeFloatingPlayer

let videoID = "f0NdOE5GTgo"

// Initiates Player with an empty details view
YTFPlayer.initYTF(with: UIView(), videoID: videoID)
YTFPlayer.showYTFView(viewController: self)

// Initiates Player with a tableView with other content
YTFPlayer.initYTF(with: tableView, tableCellNibName: "VideoCell", tableCellReuseIdentifier: "videoCell", videoID: videoID)
YTFPlayer.showYTFView(viewController: self)

// Remove Player
finishYTFView(animated: true)

```

Finally, use the `finishYTFView()` method to remove the Player.


## Author

Advaita Pandya, adipandya@gmail.com

## License

YouTubeFloatingPlayer is available under the GNU GPLv3 license. See the LICENSE file for more info.
