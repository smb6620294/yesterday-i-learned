- The answer to hiding secrets in Android apps is: [it is impossible](https://rammic.github.io/2015/07/28/hiding-secrets-in-android-apps/).
- You can view secure content on your secondary display [if you say it is secure](https://github.com/Genymobile/scrcpy/commit/1fdde490fd2a0b89680a2b5da5e5274192398023).
- There is a special "pinterest mode" for RecyclerView, called [StaggeredGridLayoutManager](https://abhiandroid.com/materialdesign/recyclerview).
- [Streamed install](https://stackoverflow.com/questions/55524302/what-is-performing-streamed-install) (with `cmd package`) installs an APK without having adb save the file somewhere on the device first, which `pm` used to do.
- Being confusing is [recommended](https://stackoverflow.com/a/14932717/1558430).
- Before you truly understand what it is, [`Fragment`](https://developer.android.com/reference/android/app/Fragment) is already deprecated. Fragments may have been [the separate panes in tablet mode](https://developer.android.com/guide/components/fragments), for example. Layouts can contain Fragments.
- [Webview session storage](https://forums.adobe.com/thread/2350512) available was unlimited for Android versions 4.1 and 4.3, but not 4.2 and 4.4, which had 10MB.
- Your package id [must](https://developer.android.com/studio/build/application-id) have at least one dot in it, so it can't be `com`.
- `JobIntentService`. A "job intent service" whose "job" is to "serve job intents". Or does it "serve intent jobs"? Or "job service intents"? Oh well. But after all that, what does it enque? ["Work"](https://android.jlelse.eu/keep-those-background-services-working-when-targeting-android-oreo-sdk-26-cbf6cc2bdb7f). `JobIntentService.enqueueWork()`.
- You may track if a _specific_ user uninstalls your app by setting up a silent push notification (or alarm, or scheduled task) that asks the app to ping your own server with your (semi-unique) Google advertising ID. When your app no longer pings back, the user uninstalled your app.
- ["If you target Android 8.0 (API level 26) and post a notification without specifying a notification channel, the notification does not appear and the system logs an error."](https://developer.android.com/training/notify-user/channels)
- `minSdkVersion=x` prevents the APK from being installed on anything less than. `targetSdkVersion=x` disables extra compatibility code that is run to keep the APK compatible with version x.
- Android Studio 0.80 beta is, by default, [broken](http://stackoverflow.com/questions/24465289/android-studio-failure-install-failed-older-sdk).
- Handling menu clicks is as stupid as you want it to be, but [here is a simpler one](http://stackoverflow.com/a/7480103/1558430)
- For whatever reason, [it is impossible to set a negative value on a NumberPicker](http://stackoverflow.com/questions/20968561/android-numberpicker-negative-values). You can only subtract the value by a negative number after the fact.
- Do know what these mean: activity/fragment lifecycles, device rotation, services, broadcasts, background tasks, asynchronous tasks, views, adapters, recyclerview, "view holder pattern"
- Strings are put inside `project_root/app/src/main/res/values/strings.xml`, because nested folders are the best.
- [The plus thing in the XML](http://developer.android.com/training/basics/firstapp/building-ui.html), like `android:id="@+id/edit_message"`, is required only for the line that defines it.
- `android:hint` are placeholder texts.
- [`layout_weight` is a relative number](http://stackoverflow.com/questions/3995825/what-does-androidlayout-weight-mean). A `layout_weight` of 1 means 100% of the width _IF_ the control happens to be the only control inside a `LinearView` with the weight specified. If two controls have the weight specified (say 1, 1), then each control shares 50% of the width.
- If `layout_weight` is given, [then](http://developer.android.com/training/basics/firstapp/building-ui.html) `layout_width` is useless (irrelevant), and should be set to 0dp or 0px.
- The back button does ["back navigation"](http://developer.android.com/design/patterns/navigation.html) (whichever activity shown in reverse chronological order); the in-app backs do "up navigation". The term "up" refers to the hierarchical parent of the current activity, a hierarchy you declare in `AndroidManifest.xml`.
- Putting a library into `libs/` seems to do it.
- There are project (`./build.gradle`) and app-level (`./app/build.gradle`) gradle files. The former defines dependencies, and the latter uses them.
- If gradle is too old, update the `classpath 'com.android.tools.build:gradle:2.1.2'`... in the gradle file. Gradle will update itself. [True fact.](http://stackoverflow.com/questions/17634708/android-studio-upgraded-from-0-1-9-to-0-2-0-causing-gradle-build-errors-now/17648742#17648742)
- Order in the layout xml files matters.
- The project's JDK settings is in File > Project Structure, which is not in Settings for studio.
- If you don't know what fresh hell you are doing, [here is a layouts cheat sheet](http://labs.udacity.com/images/Layout-Cheat-Sheet.pdf).
- Accessing the Internet on the main thread, get this, raises the `NetworkOnMainThreadException`.
- [AsyncTask](http://stackoverflow.com/questions/3921816/can-i-pass-different-types-of-parameters-to-an-asynctask-in-android) takes just one type of parameter, but you can use "the setter" (?) to use additional types, or simply [pass in an `Object`](http://stackoverflow.com/a/9077177) and re-cast from there.
- ["The difference between Handler and AsyncTask is: Use AsyncTask when Caller thread is a UI Thread."](http://stackoverflow.com/a/9800870)
- It is near impossible to [conjure a popup from a non-activity class](http://stackoverflow.com/a/31221646).
- `(an AsyncTask).get()` [immediately gets the value from its execute()](http://stackoverflow.com/a/10972142). Then again, that is a synchronous move.
- `Activity` [apparently](http://stackoverflow.com/a/9192916/1558430) extends `Context`.
- `Application` also extends `Context`.
- Find your dependency versions on [this website](http://search.maven.org/#search%7Cga%7C1%7Cio.reactivex.rxjava). It only searches on mavenCentral, I think.
- [Two-way binding is **not** natively supported](https://medium.com/@fabioCollini/android-data-binding-f9f9d3afc761#.pfcgcnfo5) by the designer thing, but there are lots of [one-way binding libraries](https://developer.android.com/topic/libraries/data-binding/index.html) available.
- To use that `com.android.databinding` plugin, the layout file must have `<Layout>` as the root, not anything else, like `<LinearLayout>`.
- [Java 8 must be explicitly enabled](http://stackoverflow.com/a/37004259/1558430)
- The superclass of your activity has a [`setTitle()`](http://stackoverflow.com/questions/3975550/android-how-to-change-the-application-title) that does what you think it does.
- [Loser answered the wrong base64 question](http://stackoverflow.com/a/29383697/1558430), but it works. [This should work.](http://stackoverflow.com/a/15683305/1558430)
- Two apps signed with the same key can [securely share code and data](https://developer.android.com/studio/publish/app-signing.html#considerations).
- adbd cannot run as root in production builds.
- The default support library already supports [automatic day/night theming](https://android-developers.googleblog.com/2016/02/android-support-library-232.html). You just need to specify `AppCompatDelegate.MODE_NIGHT_AUTO` and it will be themed for you.
- Burak says [`Serializable` is a form of reflection, and has poor performance.](https://android.jlelse.eu/yet-another-awesome-kotlin-feature-parcelize-5439718ba220)
- In some cases, [`onDestroy` is never called when an activity is destroyed.](https://academy.realm.io/posts/sf-fabien-davos-modern-android-ditching-activities-fragments/)
- Sometimes you might want to check if you can run code based on the SDK version with which your app is built (like `Build.VERSION.SDK_INT >= Build.VERSION_CODES.HONEYCOMB_MR2`). Actually, I don't think you'll ever need to do that.
- [try-with-resources is only supported if your minSdkVersion is set to 19 or higher.](https://stackoverflow.com/a/24290875/1558430) It looks like `try (foo = new SomeResourceLikeAFile()) { foo... }`. Multiple resources can be tried by separating with a `;`.
- `startActivity` accepts an `Intent` rather than `Activity` because reasons.
- If even one of your neurons fire up, you would have noticed that `new Intent(CurrentActivity.this, ...)` and `new Intent(this, ...)` are identical statements.
- IDs are under_scored. Variables are camelCased, As always, because reasons.
- It is possible to name your package using someone else's domain, like `com.microsoft.lol`.
- "Target SDK version" is the level at which you can use the SDK's features. ["Min SDK version"][stackoverflow 14] is the level at which you, the developer, have made sure the app still works by handling missing features properly.
- The API level of a [pre-release](https://developer.android.com/studio/releases/platforms#P_preview) version of Android is not a number. For P preview, the API level is just "P".
- The `R` class is [a public static final class that only contains resource-related attributes](https://stackoverflow.com/questions/6804053/understand-the-r-class-in-android) for your code to use.
- `Drawable` can be [lots of things](https://developer.android.com/guide/topics/resources/drawable-resource). PNG, JPG, GIF, XML... unfornately none of those XML formats are SVG.
- You can create a vector asset inside `File -> New -> Vector Asset`.
- Whether your activity has a certain theme doesn't get set in your layout xml (`res/layout/*.xml`), but in [`AndroidManifest.xml`](https://stackoverflow.com/a/25863690/1558430), because FUCK you.
- [You can display a downloaded image without first saving it somewhere](https://stackoverflow.com/a/6407554/1558430).
- "`@aar` is Gradle’s “Artifact only” notation that excludes dependencies by default."
- `setContentView(R.layout.main)` controls which activity shows which layout. In this case, it shows `res/layout/main.xml`. [You call it inside `onCreate` usually](https://www.quora.com/In-Android-we-are-using-setContentView-function-in-almost-all-java-classes-What-does-it-do-to-our-application). Interestingly, [that "view" can also be a button](https://stackoverflow.com/a/24706566/1558430).
- A notification has no actions by default. To have it, say, bring the app back up, [you need to give it an intent that's equivalent to one where the user tapped on the icon from the launcher](https://stackoverflow.com/a/18426787/1558430), and then `setContentIntent` to the builder.
- When the docs say a method "is deprecated", it doesn't necessarily mean all methods with that name are deprecated. It just means a method with that name _and signature_ is deprecated.
- [The fused location provider is part of google play services.](https://medium.com/@ssaurel/getting-gps-location-on-android-with-fused-location-provider-api-1001eb549089)
- If you are absolutely sure that you requested a permission using the `<uses-permission android:name="android.permission.INTERNET "/>` tag, but it isn't working for some reason, notice there should be no space after the word `INTERNET`. Idiot.
- The "builder" pattern appears to create new objects, whose instances have successively more attributes added (hence "building"), and the final `build()` command returns the thing you have been trying to build all along. This allows a developer to call flexible methods in a strict language like Java, without overloading a method with a different number of parameters.
- The [`m` and `s` variable prefixes](https://stackoverflow.com/questions/2092098/why-do-most-fields-class-members-in-android-tutorial-start-with-m) actually only concern apps that are to be contributed to the AOSP project, and should not be used in your personal projects.
- You can catch fatal exceptions (they are `Throwable`s), but [they should only be caught at the topmost layer](https://softwareengineering.stackexchange.com/questions/167242/where-should-i-handle-fatal-exceptions).
- A [`SharedPreferences`](https://developer.android.com/reference/android/content/SharedPreferences) lets you `getString()`, but it doesn't let you `putString()`. Classic Android. [You need to get the prefs' "editor" through `prefs.edit()`](https://blog.teamtreehouse.com/making-sharedpreferences-easy-with-kotlin), which _then_ has a `putString()`.
- Android Go editions may have unexpected restrictions, such as [launching an activity from a service using the `SYSTEM_ALERT_WINDOW` permission](https://developer.android.com/preview/privacy/background-activity-starts).
- Apparently if your device supports P, it can potentially [just boot off an image](https://developer.android.com/topic/generic-system-image) called the generic system image (GSI). YMMV.
- You need [100GB of disk space](https://wiki.lineageos.org/devices/bacon/build) to compile LineageOS once.
- You define the app's icon in `AndroidManifest.xml` -> `manifest[application:icon]`. That `@mipmap/ic_launcher` corresponds to an `ic_launcher.xml`, which has `<adaptive-icon>` inside.
- Apps can [export a service](https://developer.android.com/guide/topics/manifest/service-element#exported). With `android:exported="true"`, a service can be invoked by another application. Without that, an app can have a service _but other applications cannot see it_ (unless you use MyAndroidTools or something).
- [`android.*` packages (are supposed to) come with the system](https://stackoverflow.com/a/51280256/1558430), while `androidx.*` packages come with the app.
- Displaying a button over something else is surprisingly difficult without absolute positioning or z-index.
- You cannot [have a string reference another one](https://stackoverflow.com/questions/4746058/reference-one-string-from-another-string-in-strings-xml) like `<string name="string_default">@string/string1 TEST</string>`, but entire substitutions like `<string name="string_default">@string/string1</string>` are fine.
- To make a [scrollable `ConstraintLayout`](https://stackoverflow.com/questions/43098150/android-how-to-make-a-scrollable-constraintlayout), really put a `ScrollView` outside the `ConstraintLayout`.
- [`xmlns:tools="http://schemas.android.com/tools"`](https://stackoverflow.com/questions/15368386/what-is-the-meaning-of-xmlnstools-in-android-xml-layout) means every `tools:abc` uses that schema, and that is the namespace in this element. There is no need to redeclare it in children elements.
- [`RecyclerView`s](https://developer.android.com/reference/android/support/v7/widget/RecyclerView) were created because layout inflation (turning XML into whatever) is such a costly operation that Android would rather not do that for the same type of content.
- Use [`getResources().getString(R.string.MY_STRING)`](https://stackoverflow.com/a/7454481/1558430) to load a string in your class. If your class is not an instance of `Context` (for example, not an `Activity`), you don't get that method.
- To build an Android app with no interface, and have Android Studio not complain about "Default Activity not found", [go to "Edit Configurations" and have it launch "Nothing"](https://github.com/android/input-samples/issues/18#issuecomment-256698312).
- `tools:context` is [only used by the UI editor](https://stackoverflow.com/questions/11078487/whats-toolscontext-in-android-layout-files) when rendering the preview, for things that require knowledge coming from the activity. Omitting it does not impact your app running.
- `findViewById` is one way to work with your activity files, but if you are using Kotlin, [there is an extension](https://antonioleiva.com/kotlin-android-extensions/) called `kotlinx.android.synthetic` that lets you auto-import these items. People say it's no longer best practice though, so look up [view binding](https://developer.android.com/topic/libraries/view-binding), some official practice.
- [XML (layout) filenames cannot have capital letters](https://stackoverflow.com/questions/35543899/error-f-is-not-a-valid-file-based-resource-name-character-file-based-resourc/35566391).
