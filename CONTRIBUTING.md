By submitting a pull request, you represent that you have the right to license
your contribution to Apple and the community, and agree by submitting the patch
that your contributions are licensed under the [Swift
license](https://swift.org/LICENSE.txt).

---

Before submitting the pull request, please make sure you have tested your
changes and that they follow the Swift project [guidelines for contributing
code](https://swift.org/contributing/#contributing-code).

---

The [Swift CI](https://ci.swift.org/) is triggered by writing a comment on this PR addressed to the GitHub user @swift-ci. Different tests will run depending on the specific comment that you use. The currently available comments are:

**Smoke Testing**

        Platform     | Comment
        ------------ | -------------
        All supported platforms     | @swift-ci Please smoke test
        All supported platforms     | @swift-ci Please smoke test and merge
        OS X platform               | @swift-ci Please smoke test OS X platform
        Linux platform              | @swift-ci Please smoke test Linux platform

A smoke test on macOS does the following:

1. Builds the compiler incrementally.
2. Builds the standard library only for macOS. Simulator standard libraries and
   device standard libraries are not built.
3. lldb is not built.
4. The test and validation-test targets are run only for macOS. The optimized
   version of these tests are not run.

A smoke test on Linux does the following:

1. Builds the compiler incrementally.
2. Builds the standard library incrementally.
3. lldb is built incrementally.
4. The swift test and validation-test targets are run. The optimized version of these
   tests are not run.
5. lldb is tested.

**Validation Testing**

        Platform     | Comment
        ------------ | -------------
        All supported platforms     | @swift-ci Please test
        All supported platforms     | @swift-ci Please clean test
        All supported platforms     | @swift-ci Please test and merge
        OS X platform               | @swift-ci Please test OS X platform
        OS X platform               | @swift-ci Please clean test OS X platform
        OS X platform               | @swift-ci Please benchmark
        Linux platform              | @swift-ci Please test Linux platform
        Linux platform              | @swift-ci Please clean test Linux platform


**Lint Testing**

        Language     | Comment
        ------------ | -------------
        Python       | @swift-ci Please Python lint

Note: Only members of the Apple organization can trigger swift-ci.
