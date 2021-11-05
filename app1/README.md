# TabLayout tab width bug

This application demonstrates that
a [TabLayout](https://developer.android.com/reference/com/google/android/material/tabs/TabLayout) which has
a [tabMode](https://developer.android.com/reference/com/google/android/material/tabs/TabLayout#attr_TabLayout_tabMode)
value
of [fixed](https://developer.android.com/reference/com/google/android/material/tabs/TabLayout#MODE_FIXED)
and
a [tabGravity](https://developer.android.com/reference/com/google/android/material/tabs/TabLayout#attr_TabLayout_tabGravity)
value
of [fill](https://developer.android.com/reference/com/google/android/material/tabs/TabLayout#GRAVITY_FILL) (as
in the layout file [here](src/main/res/layout/activity_main.xml))
results in the first tab having excessive start and end padding on some devices
(e.g. the Moto G8 Plus in landscape orientation), as follows:

![Screenshot of TabLayout bug](screenshots/TabLayoutBugScreenshot.png)

The fix (as demonstrated in [app2](../app2)) is to give
the [TabLayout](https://developer.android.com/reference/com/google/android/material/tabs/TabLayout)
a [tabMaxWidth](https://developer.android.com/reference/com/google/android/material/tabs/TabLayout#attr_TabLayout_tabMaxWidth)
value different to the default value of `264dp`. Note
that [TabLayout](https://developer.android.com/reference/com/google/android/material/tabs/TabLayout)s get a
default [tabMaxWidth](https://developer.android.com/reference/com/google/android/material/tabs/TabLayout#attr_TabLayout_tabMaxWidth)
value via the `Base.Widget.Design.TabLayout` style that's defined in
the `com.google.android.material:material` library's `res` folder.

#### Additional links

* See [here](https://github.com/material-components/material-components-android/issues/1856) for the
  associated issue in
  the [material-components-android](https://github.com/material-components/material-components-android) GitHub
  repository.
