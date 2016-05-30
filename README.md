# ArcanistUncrustifyLinter

## What is Uncrustify

Uncrustify make code formatting beautiful. It needs configrations, I couldn't find a good configuration for iOS developer on Objective-C.

Here's a repo collecting pretty uncrustify config for iOS developer.

You can distribute your configurations over pull request.

## What is ArcanistUncrustifyLinter

when you use phabricator to manage your iOS projects, you can use ArcanistUncrustifyLinter with Uncrustify to help you format code.

## Requirements

1. Tested with Xcode 4.6+ (also works in Xcode 5) on OS X 10.7 or higher.
- Uncrustify 0.60 higher (0.60 has a bug for Objective-C block, so install master HEAD or higher in the future)
- BBUncrustifyPlugin-Xcode

## Installation

### Uncrustify

1. using [HomeBrew](http://mxcl.github.io/homebrew/) install Uncrustify
```
brew install uncrustify --HEAD
```
- install [BBUncrustifyPlugin-Xcode](https://github.com/benoitsan/BBUncrustifyPlugin-Xcode/blob/master/README.md#installation)
- clone this repo to `~/.uncrustify/` or other folder as [BBUncrustifyPlugin-Xcode](https://github.com/benoitsan/BBUncrustifyPlugin-Xcode/blob/master/README.md#how-to-customize-the-uncrustify-configuration) said.
```
git clone https://github.com/dijkst/uncrustify-config-ios.git ~/.uncrustify
```

### ArcanistUncrustifyLinter

### Custom

Default settings disable the alignment of continued assignment or variable definition. If you need them, just set `align_assign_span`, `align_var_def_span` and `align_oc_msg_spec_span` to `1`.


## Example

#### ~~align code~~ (unsupported, please read `Custom`):

before:
``` objective-c
NSString *const BBUncrustifyOptionEvictCommentInsertion = @"evictCommentInsertion";
NSString *const BBUncrustifyOptionSourceFilename = @"sourceFilename";
NSString *const BBUncrustifyOptionSupplementalConfigurationFolders = @"supplementalConfigurationFolders";
```
after:
``` objective-c
NSString *const BBUncrustifyOptionEvictCommentInsertion            = @"evictCommentInsertion";
NSString *const BBUncrustifyOptionSourceFilename                   = @"sourceFilename";
NSString *const BBUncrustifyOptionSupplementalConfigurationFolders = @"supplementalConfigurationFolders";
```

#### remove space:

before:
``` objective-c
-( void )viewWillEnter ;
```
after:
``` objective-c
- (void)viewWillEnter;
```

#### insert newline between methods

``` objective-c
- (void)a {
}
- (void)b{
}
```
after:
``` objective-c
- (void)a {
}

- (void)b {
}
```

and so on.

## License

uncrustify-config-ios is available under the MIT license.


# Demo uncrustify-config

https://github.com/EmoneyCN/uncrustify-config-ios