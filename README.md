
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
7. Product > Scheme > Manage Schemes > {Paid,Free} > Edit
8. Ensure {Paid,Free} schemes point to "{Debug,Profile,Release} {Paid,Free}" configurations
9. View > Navigators > Project > Runner/Runner/Info
10. Add a key value pair, "Flavor", "$(PRODUCT_FLAVOR)"
11. View > Navigators > Project > PROJECT > Runner > Build Settings
12. Add User-Defined Settings > PRODUCT_FLAVOR > {free/paid}
13. Add method channel to ios/Runner/AppDelegate.m

The above summarizes the state of that integration test as mravn
committed in August of 2017.

And this was roughly the state before May 11th, 2020. The next steps
explain what happens then.

1. View > Navigators > Project > Runner/Runner/Info
2. Remove Bundle Display Name and set Bundle Name to PRODUCT_NAME
