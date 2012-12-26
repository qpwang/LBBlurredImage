LBBlurredImage
============

LBBlurredImage is an UIImageView category that permit to set an image and make this blurred.

Here are an example of what you can achieve:

![](https://raw.github.com/lukabernardi/LBBlurredImage/master/Resources/SimulatorScreenshot.png)

Installation & Use
============

### Installation

This code must be used with deploy targer 6.0+ and under ARC. 
If your code doesn't use ARC you can [mark this source with the compiler flag](http://www.codeography.com/2011/10/10/making-arc-and-non-arc-play-nice.html) `-fobjc-arc` 

- Just grab the two file named `UIImageView+LBBlurredImage.h` & `UIImageView+LBBlurredImage.m` in the Additions group into your project and link with CoreImage.framework .
- `#import "UIImageView+LBBlurredImage.h"` where you need it.

### Use

``` objective-c
[self.imageView setImageToBlur:[UIImage imageNamed:@"example"]
                    blurRadius:kLBBlurredImageDefaultBlurRadius
               completionBlock:^(NSError *error){
                   NSLog(@"The blurred image has been setted");
               }];
```

The generation of the blurred image is made on a background thread, for this reason a completion block is provided. The completionBlock is dispatched on the main thread when the image was generated and set to the UIImageView.

License
============
LBBlurredImage is available under the MIT license. See the LICENSE file for more info.