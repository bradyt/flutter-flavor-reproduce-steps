
This project tries to document how to recreate the flavors app at the
following location:

- https://github.com/flutter/flutter/commits/master/dev/integration_tests/flavors

The focus is on iOS.

Steps:

1. flutter create . --project-name flavors -i objc -a android
2. open ios/Runner.xcworkspace
3. Product > Scheme > Manage Schemes
4. Rename scheme "Runner" to "Free", duplicate as "Paid", check "Shared"
5. View > Navigators > Project > PROJECT > Runner > Info > Configurations
6. Copy Debug, Release, Profile, and add " Paid" or " Free"

