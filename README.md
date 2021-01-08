#### BASE
* **What is the Android Architecture?** 
![image](assets/android-architecture.png)

* **Tell all the Android application components.** 
    - Android application architecture has the following components:
        - Activities - Provides the window in which the app draws its UI
        - Services − It will perform background functionalities
        - Intent  & Broadcast Receivers − It will perform the inter connection between activities and the data passing mechanism
        - Content Providers − It will share the data between applications
        - Resource Externalization − strings and graphics
        - Notification − light, sound, icon, notification, dialog box and toast
<br> [Learn more here](https://developer.android.com/guide/components/fundamentals.html#Components)

* **Describe Android application components.** 
    - A **Activity** represents a single screen with a user interface, in-short Activity performs actions on the screen. An activity provides the window in which the app draws its UI. This window typically fills the screen, but may be smaller than the screen and float on top of other windows. Generally, one activity implements one screen in an app. For instance, one of an app’s activities may implement a Preferences screen, while another activity implements a Select Photo screen. In new architectural approaches, there is only one activity for the entire application, and it controls the fragments that interact with the user.

    - A **Service** is an application component that can perform long-running operations in the background, and it doesn't provide a user interface. Another application component can start a service, and it continues to run in the background even if the user switches to another application. Additionally, a component can bind to a service to interact with it and even perform interprocess communication (IPC). For example, a service can handle network transactions, play music, perform file I/O, or interact with a content provider, all from the background.

    - A **Broadcast Receivers** (receiver) is an Android component which allows you to register for system or application events. Android apps can send or receive broadcast messages from the Android system and other Android apps, similar to the publish-subscribe design pattern. These broadcasts are sent when an event of interest occurs. For example, the Android system sends broadcasts when various system events occur, such as when the system boots up or the device starts charging. Apps can also send custom broadcasts, for example, to notify other apps of something that they might be interested in (for example, some new data has been downloaded).

    - A **Content Provider** manages access to a central repository of data. You implement a provider as one or more classes in an Android application, along with elements in the manifest file. One of your classes implements a subclass `ContentProvider`, which is the interface between your provider and other applications. Although content providers are meant to make data available to other applications, you may of course have activities in your application that allow the user to query and modify the data managed by your provider.

* **What is the project structure of an Android Application?** 
    - [Learn more here](https://developer.android.com/studio/projects)

* **What is `Context`? How is it used?** 
    - A **Context** is a handle to the system; it provides services like resolving resources, obtaining access to databases and preferences, and so on. An Android app has activities. Context is like a handle to the environment your application is currently running in.
    - **Application Context:** This context is tied to the lifecycle of an application. The application context can be used where you need a context whose lifecycle is separate from the current context or when you are passing a context beyond the scope of an activity.
    - **Activity Context:** This context is available in an activity. This context is tied to the lifecycle of an activity. The activity context should be used when you are passing the context in the scope of an activity or you need the context whose lifecycle is attached to the current context.
<br>[Learn more here](https://blog.mindorks.com/understanding-context-in-android-application-330913e32514)

* What is AndroidManifest.xml used for? Give examples of what kind of data you would add to it. [Learn more here](http://developer.android.com/guide/topics/manifest/manifest-intro.html)

* **What is `AndroidManifest.xml`?** 
    - **Manifest**: Every application must have an AndroidManifest.xml file (with precisely that name) in its root directory. The manifest presents essential information about the application to the Android system, information the system must have before it can run any of the application's code. It contains information of your package, including components of the application such as activities, services, broadcast receivers, content providers etc.
    - **R.Java:** It is an auto-generated file by aapt (Android Asset Packaging Tool) that contains resource IDs for all the resources of res/ directory. 
<br>[Learn more here](https://developer.android.com/guide/topics/manifest/manifest-intro)

* **What is `Application` class?**
    - The Application class in Android is the base class within an Android app that contains all other components such as activities and services. The Application class, or any subclass of the Application class, is instantiated before any other class when the process for your application/package is created.


#### ACTIVITY

* **What are the four states of the Activity Lifecycle?** 
    The Android OS uses a priority queue to assist in managing activities running on the device. Based on the state a particular Android activity is in, it will be assigned a certain priority within the OS. This priority system helps Android identify activities that are no longer in use, allowing the OS to reclaim memory and resources.

    These states can be broken into three main groups as follows:

        - **Active** or Running - Activities are considered active or running if they are in the foreground, also known as the top of the activity stack. This is considered the highest priority activity in the Android Activity stack, and as such will only be killed by the OS in extreme situations, such as if the activity tries to use more memory than is available on the device as this could cause the UI to become unresponsive.

        - **Paused** - When the device goes to sleep, or an activity is still visible but partially hidden by a new, non-full-sized or transparent activity, the activity is considered paused. Paused activities are still alive, that is, they maintain all state and member information, and remain attached to the window manager. This is considered to be the second highest priority activity in the Android Activity stack and, as such, will only be killed by the OS if killing this activity will satisfy the resource requirements needed to keep the Active/Running Activity stable and responsive.

        - **Stopped** - Activities that are completely obscured by another activity are considered stopped or in the background. Stopped activities still try to retain their state and member information for as long as possible, but stopped activities are considered to be the lowest priority of the three states and, as such, the OS will kill activities in this state first to satisfy the resource requirements of higher priority activities.
[Learn more here](https://developer.android.com/reference/android/app/Activity.html#ActivityLifecycle)

* **What is `Activity` and its lifecycle?** 
    - Activities are basically containers or windows to the user interface.
    * ```OnCreate()```: This is when the view is first created. This is normally where we create views, get data from bundles etc.</br>
  * ```OnStart()```: Called when the activity is becoming visible to the user. Followed by onResume() if the activity comes to the foreground, or onStop() if it becomes hidden.</br>
  * ```OnResume()```: Called when the activity will start interacting with the user. At this point your activity is at the top of the activity stack, with user input going to it.</br>
  * ```OnPause()```: Called as part of the activity lifecycle when an activity is going into the background, but has not (yet) been killed.</br>
  * ```OnStop()```: Called when you are no longer visible to the user.</br>
  * ```OnDestroy()```: Called when the activity is finishing</br>
  * ```OnRestart()```: Called after your activity has been stopped, prior to it being started again</br>
![image](assets/activity_lifecycle.png)
<br>[Learn more here](https://www.youtube.com/watch?v=RiFui-i-s-o)


* **What is the difference between onCreate() and onStart()** 
    - The onCreate() method is called once during the Activity lifecycle, either when the application starts, or when the Activity has been destroyed and then recreated, for example during a configuration change.
    - The onStart() method is called whenever the Activity becomes visible to the user, typically after onCreate() or onRestart().
<br>[Learn more here](https://www.youtube.com/watch?v=RiFui-i-s-o)

* **When only onDestroy is called for an activity without onPause() and onStop()?** 
    - If finish() is called in the OnCreate method of an activity, the system will invoke onDestroy() method directly.
<br>[Learn more here](https://www.youtube.com/watch?v=QSxcLnZ1-RU)

* **Why do we need to call setContentView() in onCreate() of Activity class?** 
    - As onCreate() of an Activity is called only once, this is the point where most initialization should go. It is inefficient to set the content in onResume() or onStart() (which are called multiple times) as the setContentView() is a heavy operation.
<br>[Learn more here](https://www.youtube.com/watch?v=zeYK8JdMOi8)

* **What is onSavedInstanceState() and onRestoreInstanceState() in activity?**
    - **OnRestoreInstanceState()** - When activity is recreated after it was previously destroyed, we can recover the saved state from the Bundle that the system passes to the activity. Both the onCreate() and onRestoreInstanceState() callback methods receive the same Bundle that contains the instance state information. But because the onCreate() method is called whether the system is creating a new instance of your activity or recreating a previous one, you must check whether the state Bundle is null before you attempt to read it. If it is null, then the system is creating a new instance of the activity, instead of restoring a previous one that was destroyed.
    - **onSaveInstanceState**() - is a method used to store data before pausing the activity.

* **How does the activity respond when the user rotates the screen?**
    - When the screen is rotated, the current instance of activity is destroyed a new instance of the Activity is created in the new orientation. The onRestart() method is invoked first when a screen is rotated. The other lifecycle methods get invoked in the similar flow as they were when the activity was first created.


* **How to prevent the data from reloading and resetting when the screen is rotated?**
    - The most common approach these days would be to use a combination of ViewModels and onSaveInstanceState(). So how we do we that?
       * Basics of [ViewModel](https://developer.android.com/reference/android/arch/lifecycle/ViewModel): A ViewModel is LifeCycle-Aware. In other words, a ViewModel will not be destroyed if its owner is destroyed for a configuration change (e.g. rotation). The new instance of the owner will just re-connected to the existing ViewModel. So if you rotate an Activity three times, you have just created three different Activity instances, but you only have one ViewModel.
       * So the common practice is to store data in the ViewModel class (since it persists data during configuration changes) and use OnSaveInstanceState to store small amounts of UI data.
       * For instance, let’s say we have a search screen and the user has entered a query in the Edittext. This results in a list of items being displayed in the RecyclerView. Now if the screen is rotated, the ideal way to prevent resetting of data would be to store the list of search items in the ViewModel and the query text user has entered in the OnSaveInstanceState method of the activity.</br>

  
* **What’s the difference between FLAG_ACTIVITY_CLEAR_TASK and FLAG_ACTIVITY_CLEAR_TOP?**</br>
  * **FLAG_ACTIVITY_CLEAR_TASK** is used to clear all the activities from the task including any existing instances of the class invoked. The Activity launched by intent becomes the new root of the otherwise empty task list. This flag has to be used in conjunction with FLAG_ ACTIVITY_NEW_TASK.</br>
  * **FLAG_ACTIVITY_CLEAR_TOP** on the other hand, if set and if an old instance of this Activity exists in the task list then barring that all the other activities are removed and that old activity becomes the root of the task list. Else if there’s no instance of that activity then a new instance of it is made the root of the task list. Using **FLAG_ACTIVITY_NEW_TASK** in conjunction is a good practice, though not necessary.</br>  
  
* **Mention two ways to clear the back stack of Activities when a new Activity is called using intent**</br>
   * The first approach is to use a FLAG_ACTIVITY_CLEAR_TOP flag. The second way is by using FLAG_ACTIVITY_CLEAR_TASK and FLAG_ACTIVITY_NEW_TASK in conjunction.</br>
  
  
  

#### CONTENT PROVIDERS

* What is a ContentProvider and what is it typically used for?


* **Describe content providers**</br>
  * A ContentProvider provides data from one application to another, when requested. It manages access to a structured set of data.  It provides mechanisms for defining data security. ContentProvider is the standard interface that connects data in one process with code running in another process.</br>  
  * When you want to access data in a **ContentProvider**, you must instead use the ContentResolver object in your application’s Context to communicate with the provider as a client. The provider object receives data requests from clients, performs the requested action, and returns the results.</br>
  <br>[Learn more here](http://developer.android.com/guide/topics/providers/content-providers.html)
  
  
* **Access data using Content Provider:**</br>
  * Start by making sure your Android application has the necessary read access permissions. Then, get access to the ContentResolver object by calling getContentResolver() on the Context object, and retrieving the data by constructing a query using ContentResolver.query().</br>
  * The ContentResolver.query() method returns a Cursor, so you can retrieve data from each column using Cursor methods.</br> 
  

#### FRAGMENTS
  
* **Describe fragments:**</br>
  * Fragment is a UI entity attached to Activity. Fragments can be reused by attaching in different activities. Activity can have multiple fragments attached to it. Fragment must be attached to an activity and its lifecycle will depend on its host activity. 
<br>[Learn more here](https://blog.mindorks.com/android-fragments-and-its-lifecycle) or [here](http://developer.android.com/guide/components/fragments.html)</br>

* **What are the four states of the Activity Lifecycle?** 
    
    Managing the lifecycle of a fragment is a lot like managing the lifecycle of an activity. Like an activity, a fragment can exist in three states:

        - **Resumed**: The fragment is visible in the running activity.

        - **Paused** - Another activity is in the foreground and has focus, but the activity in which this fragment lives is still visible (the foreground activity is partially transparent or doesn't cover the entire screen).

        - **Stopped** - The fragment isn't visible. Either the host activity has been stopped or the fragment has been removed from the activity but added to the back stack. A stopped fragment is still alive (all state and member information is retained by the system). However, it is no longer visible to the user and is killed if the activity is killed.

 
* **Describe fragment lifecycle**</br>
  * ```onAttach()``` : The fragment instance is associated with an activity instance.The fragment and the activity is not fully initialized. Typically you get in this method a reference to the activity which uses the fragment for further initialization work.
  * ```onCreate()``` : The system calls this method when creating the fragment. You should initialize essential components of the fragment that you want to retain when the fragment is paused or stopped, then resumed.
  * ```onCreateView()``` : The system calls this callback when it’s time for the fragment to draw its user interface for the first time. To draw a UI for your fragment, you must return a View component from this method that is the root of your fragment’s layout. You can return null if the fragment does not provide a UI.
  * ```onActivityCreated()``` : The onActivityCreated() is called after the onCreateView() method when the host activity is created. Activity and fragment instance have been created as well as the view hierarchy of the activity. At this point, view can be accessed with the findViewById() method. example. In this method you can instantiate objects which require a Context object
  * ```onStart()``` : The onStart() method is called once the fragment gets visible.
  * ```onResume()``` : Fragment becomes active.
  * ```onPause()``` : The system calls this method as the first indication that the user is leaving the fragment. This is usually where you should commit any changes that should be persisted beyond the current user session.
  * ```onStop()``` : Fragment going to be stopped by calling onStop()
  * ```onDestroyView()``` : Fragment view will destroy after call this method
  * ```onDestroy()``` :called to do final clean up of the fragment’s state but Not guaranteed to be called by the Android platform.</br>  
![image](assets/fragment_lifecycle.png)


* **What is the correlation between activity and fragment life cycle?**<br/>
-   Here is how Activity's and Fragment's lifecyle are called together:
![image](assets/activity-fragment-lifecycles.png)

* **What is the difference between fragments & activities. Explain the relationship between the two.**</br>
  - * An Activity is an application component that provides a screen, with which users can interact in order to do something whereas a Fragment represents a behavior or a portion of user interface in an Activity (with its own lifecycle and input events, and which can be added or removed at will).
[Learn more here](https://stackoverflow.com/questions/10478233/why-fragments-and-when-to-use-fragments-instead-of-activities) or [here](https://stackoverflow.com/a/45252253/497132)) </br>
  
  
* **When should you use a fragment rather than an activity?**</br>
  * When there are ui components that are going to be used across multiple activities. 
  * When there are multiple views that can be displayed side by side (viewPager tabs)
  * When you have data that needs to be persisted across Activity restarts (such as retained fragments)</br>

  
* **Difference between adding/replacing fragment in backstack?**</br>
  * **replace** removes the existing fragment and adds a new fragment. This means when you press back button the fragment that got replaced will be created with its onCreateView being invoked.
  * **add** retains the existing fragments and adds a new fragment that means existing fragment will be active and they wont be in ‘paused’ state hence when a back button is pressed onCreateView is not called for the existing fragment(the fragment which was there before new fragment was added).
  * In terms of fragment’s life cycle events onPause, onResume, onCreateView and other life cycle events will be invoked in case of replace but they wont be invoked in case of add.</br>
  [Learn more here](https://stackoverflow.com/questions/24466302/basic-difference-between-add-and-replace-method-of-fragment/24466345)

  
* **Why is it recommended to use only the default constructor to create a Fragment?**</br>
  * The reason why you should be passing parameters through bundle is because when the system restores a fragment (e.g on config change), it will automatically restore your bundle. This way you are guaranteed to restore the state of the fragment correctly to the same state the fragment was initialised with.</br>
  [Learn more here](https://www.youtube.com/watch?v=9EdvcycKP9A)
  
  
* **You’re replacing one Fragment with another — how do you ensure that the user can return to the previous Fragment, by pressing the Back button?**</br>
  * We need to save each Fragment transaction to the backstack, by calling ```addToBackStack()``` before you ```commit()``` that transaction</br>
 
  
* **Callbacks invoked during addition of a fragment to back stack and while popping back from back stack:**</br>
  * ```addOnBackStackChangedListener``` is called when fragment is added or removed from the backstack. Use this [link](https://why-android.com/2016/03/29/learn-how-to-use-the-onbackstackchangedlistener/) for reference</br>
  
  
* **What are retained fragments**</br>
  * By default, Fragments are destroyed and recreated along with their parent Activity’s when a configuration change occurs. Calling ```setRetainInstance(true)``` allows us to bypass this destroy-and-recreate cycle, signaling the system to retain the current instance of the fragment when the activity is recreated.</br>
  
  
* **Difference between FragmentPagerAdapter vs FragmentStatePagerAdapter?**</br>
  * **FragmentPagerAdapter**: the fragment of each page the user visits will be stored in memory, although the view will be destroyed. So when the page is visible again, the view will be recreated but the fragment instance is not recreated. This can result in a significant amount of memory being used. FragmentPagerAdapter should be used when we need to store the whole fragment in memory. FragmentPagerAdapter calls ```detach(Fragment)``` on the transaction instead of ```remove(Fragment)```.
  * **FragmentStatePagerAdapter**:  the fragment instance is destroyed when it is not visible to the User, except the saved state of the fragment. This results in using only a small amount of Memory and can be useful for handling larger data sets. Should be used when we have to use dynamic fragments, like fragments with widgets, as their data could be stored in the 
savedInstanceState.Also it won't affect the performance even if there are large number of fragments.</br>


* **How would you communicate between two Fragments?** - [Learn more here](https://blog.mindorks.com/how-to-communicate-between-fragments)


#### VIEWS AND VIEWGROUPS, AND LAYOUTS

* **What is `View` in Android?** 
- The view is the component which Android provides us to design the layouts of the app. So, we can understand view as a rectangular area which is going to contain some element inside it.

A View is a superclass for all the UI components. You can also check out the official documentation of View, here. 
<br> [Learn more here](https://blog.mindorks.com/android-user-interface-view-components)

* **Difference between `View.GONE` and `View.INVISIBLE`?** 
    - `View.GONE`: This view is invisible, and it doesn't take any space for layout purposes.
    - `View.INVISIBLE`: This view is invisible, but it still takes up space for layout purposes.

* **Can you a create custom view? How?** - [Learn more here](https://blog.mindorks.com/create-your-own-custom-view)

* **What are ViewGroups and how they are different from the Views?**
    - View: View objects are the basic building blocks of User Interface(UI) elements in Android. View is a simple rectangle box which responds to the user’s actions. Examples are EditText, Button, CheckBox etc. View refers to the android.view.View class, which is the base class of all UI classes.
    - ViewGroup: ViewGroup is the invisible container. It holds View and ViewGroup. For example, LinearLayout is the ViewGroup that contains Button(View), and other Layouts also. ViewGroup is the base class for Layouts.

* **What is a Canvas?** 
*   Canvas API in Android is a drawing framework which helps us to custom design like line, circle or even a rectangle. Using these we can make any shape whichever we want according to design. 

*   The drawing of canvas happens in Bitmap, where we draw the outline and then the Paint API helps to fill color and whatever style we need. 
<br>[Learn more here](https://blog.mindorks.com/understanding-canvas-api-in-android)

* **What is a `SurfaceView`?** - [Learn more here](https://developer.android.com/reference/android/view/SurfaceView)

* **Relative Layout vs Linear Layout.** - [Learn more here](https://blog.mindorks.com/android-layout-relative-linear-frame)

* **Tell about Constraint Layout** - [Learn more here](https://blog.mindorks.com/using-constraint-layout-in-android-531e68019cd)

* **Do you know what is the view tree? How can you optimize its depth?** - [Learn more here](https://developer.android.com/reference/android/view/ViewTreeObserver)

* **How does the Touch Control and Events work in Android?** - [Learn more here](https://blog.mindorks.com/touch-control-and-events-in-android) and [here](https://www.youtube.com/watch?v=tKeYr7iV5xE)
 
   
   
* **Difference between margin & padding?**</br>
   * Padding will be space added inside the container, for instance, if it is a button, padding will be added inside the button. Margin will be space added outside the container.</br>
   
   
* **What is View Group? How are they different from Views?**</br>
   * **View**: View objects are the basic building blocks of User Interface(UI) elements in Android. View is a simple rectangle box which responds to the user's actions. Examples are EditText, Button, CheckBox etc. View refers to the ```android.view.View``` class, which is the base class of all UI classes.
   * **ViewGroup**: ViewGroup is the invisible container. It holds View and ViewGroup. For example, LinearLayout is the ViewGroup that contains Button(View), and other Layouts also. ViewGroup is the base class for Layouts.</br>   
  
  
* **What is the difference between a regular .png and a nine-patch image?**</br>
   * It is one of a resizable bitmap resource which is being used as backgrounds or other images on the device. The NinePatch class allows drawing a bitmap in nine sections. The four corners are unscaled; the middle of the image is scaled in both axes, the four edges are scaled into one axis.</br>


* **Raw folder vs Assets folder**
    - The files in both directories will be stored intact in the APK package after being packaged and will not be compiled into binary systems.

    **The differences between res/raw and assets:**

    Since `raw` is a subfolder of Resources (`res`), Android will automatically generate an ID for any file located inside it. This ID is then stored an the `R` class that will act as a reference to a file, meaning it can be easily accessed from other Android classes and methods and even in Android XML files. Using the automatically generated ID is the fastest way to have access to a file in Android.

    The Assets folder is an “appendix” directory. The `R` class does not generate IDs for the files placed there, so its less compatible with some Android classes and methods. Also, it’s much slower to access a file inside it, since you will need to get a handle to it based on a String. However some operations are more easily done by placing files in this folder, like copying a database file to the system’s memory. There’s no (easy) way to create an Android XML reference to files inside the Assets folder.

* **@id vs @+id**</br>
   * The at-symbol (`@`) at the beginning of the string indicates that the XML parser should parse and expand the rest of the ID string and identify it as an ID resource. The plus-symbol (`+`) means that this is a new resource name that must be created and added to our resources (in the `R.java` file). In other words, the `+` symbol tells Android build tools that you are declaring a new resource, `@id/` you are referring to an existing resource (predefined by `@+id/` and already exists in `R.java`.
    
   
* Describe how to implement XML namespaces.
* Explain the differences and similarities of List Views and Grid Views.
* Explain how to present different styles/drawables for a button depending
on the state of the button (pressed, selected, etc.) using XML (no Java) [[info]](http://developer.android.com/guide/topics/resources/drawable-resource.html#StateList)
* for layout\_width and layout\_height, what's the difference between match\_parent and wrap\_content?
* How do you implement Google's new Material Design in an Android application? [[info]](https://developer.android.com/training/material/get-started.html)

* **nodpi VS anydpi**</br>
   * **nodpi: Fallback** 
        - A drawable inside the `res/drawable-nodpi/`  folder is valid for any screen density. Eg. **drawable-nodpi/ic_icon.png**
        The above icon will will look small on `xxxhdpi` devices and big on `ldpi` devices.

            **drawable-hdpi/ic_icon.png** **drawable-nodpi-21/ic_icon.xml**
            In android 21 hdpi devices `ic_icon.png` will be used and in android 21 xhdpi devices `ic_icon.xml` will be used.

   * **anydpi: Takeover** 
        - A drawable inside `drawable-anydpi`  is also valid for any screen
        density but anydpi variant has more priority over any density specific variant.

            Eg. If we have **res/drawable-anydpi/ic_icon.xml** and  **res/drawable-xxxhdpi/ic_icon.png** then `ic_icon.xml` will be used even in xxxhdpi devices.

            Most of the times `-anydpi` used in conjunction with other qualifiers. A good example is  `anydpi-v21` as vector drawables were introduced in android 21 , so after that  we usually have `res/drawable-anydpi-v21/ic_icon.xml` (Vector drawable) and `res/drawable-xxhdpi/ic_icon.png`. The vector drawable (`ic_icon.xml`) will be used in all android 21+ devices and `ic_icon.png` will be used in xxhdpi devices runing in android 4.4 or older
 </br>


* **Difference between RelativeLayout and LinearLayout?**</br>
   * **Linear Layout** - Arranges elements either vertically or horizontally. i.e. in a row or column. 
   * **Relative Layout** - Arranges elements relative to parent or other elements.</br>
   
   
* **What is ConstraintLayout?**</br>
   * It allows you to create large and complex layouts with a flat view hierarchy (no nested view groups). It's similar to RelativeLayout in that all views are laid out according to relationships between sibling views and the parent layout, but it's more flexible than RelativeLayout and easier to use with Android Studio's Layout Editor.
   * [Sample Implementation](https://github.com/anitaa1990/ConstraintLayout-Sample) 
   * You can read more about how to implement a simple app with ConstraintLayout [here](https://android.jlelse.eu/learning-to-implement-constraintlayout-in-android-8ddc69fe0a1a), by yours truly :)</br>
   
   
* **When might you use a FrameLayout?**</br>
   * Frame Layouts are designed to contain a single item, making them an efficient choice when you need to display a single View.
   * If you add multiple Views to a FrameLayout then it’ll stack them one above the other, so FrameLayouts are also useful if you need overlapping Views, for example if you’re implementing an overlay or a HUD element.</br> 
   
   
* **What is Adapters?**</br>
   * An adapter responsible for converting each data entry into a View that can then be added to the AdapterView (ListView/RecyclerView).</br>
   

* **How to support different screen sizes?**</br>
   * Create a flexible layout - The best way to create a responsive layout for different screen sizes is to use ConstraintLayout as the base layout in your UI. ConstraintLayout allows you to specify the position and size for each view according to spatial relationships with other views in the layout. This way, all the views can move and stretch together as the screen size changes.
   * Create stretchable nine-patch bitmaps
   * Avoid hard-coded layout sizes - Use wrap_content or match_parent. Create alternative layouts - The app should provide alternative layouts to optimize the UI design for certain screen sizes. For eg: different UI for tablets
   * Use the smallest width qualifier.  For example, you can create a layout named main_activity that's optimized for handsets and tablets by creating different versions of the file in directories as follows:            
      * res/layout/main_activity.xml           # For handsets (smaller than 600dp available width)                      
      * res/layout-sw600dp/main_activity.xml   # For 7” tablets (600dp wide and bigger). 
      * The smallest width qualifier specifies the smallest of the screen's two sides, regardless of the device's current orientation, so it's a simple way to specify the overall screen size available for your layout.</br>
  
  
  
* **Outline the process of creating custom Views:**</br>
   * Create a class that Subclass a view
   * Create a res/values/attrs.xml file and declare the attributes you want to use with your custom View.
   * In your View class, add a constructor method, instantiate the Paint object, and retrieve your custom attributes.
   * Override either onSizeChanged() or onMeasure().
   * Draw your View by overriding onDraw().
   * [Sample Implementation](https://code.tutsplus.com/tutorials/android-sdk-creating-custom-views--mobile-14548) </br>
   
   
* **Briefly describe some ways that you can optimize View usage**</br>
   * Checking for excessive overdraw: install your app on an Android device, and then enable the "Debug GPU Overview" option.
   * Flattening your view hierarchy: inspect your view hierarchy using Android Studio’s ‘Hierarchy Viewer’ tool.
   * Measuring how long it takes each View to complete the measure, layout, and draw phases. You can also use Hierarchy Viewer to identify any parts of the rendering pipeline that you need to optimize.</br>
   
   
* **Bitmap pooling in android?**</br>
   * Bitmap pooling is a simple technique, that aims to reuse bitmaps instead of creating new ones every time. When you need a bitmap, you check a bitmap stack to see if there are any bitmaps available. If there are not bitmaps available you create a new bitmap otherwise you pop a bitmap from the stack and reuse it. Then when you are done with the bitmap, you can put it on a stack. [Find more info here](https://www.linkedin.com/pulse/performance-improvement-bitmap-pooling-android-ali-muzaffar/)</br>
   
   
* **How to load bitmap to memory?**</br>
   * [Find more info here](https://android.jlelse.eu/loading-large-bitmaps-efficiently-in-android-66826cd4ad53)</br>   
  
 

#### PERMISIONS

* **What are the permission protection levels in Android?**</br>
   * **Normal** - A lower-risk permission that gives requesting applications access to isolated application-level features, with minimal risk to other applications, the system, or the user. The system automatically grants this type of permission to a requesting application at installation, without asking for the user's explicit approval.
   * **Dangerous** - A higher-risk permission. Any dangerous permissions requested by an application may be displayed to the user and require confirmation before proceeding, or some other approach may be taken to avoid the user automatically allowing the use of such facilities.
   * **Signature** - A permission that the system grants only if the requesting application is signed with the same certificate as the application that declared the permission. If the certificates match, the system automatically grants the permission without notifying the user or asking for the user's explicit approval.
   * **SignatureOrSystem** - A permission that the system grants only to applications that are in the Android system image or that are signed with the same certificate as the application that declared the permission.

 [Learn more here](https://blog.mindorks.com/what-are-the-different-protection-levels-in-android-permission) or
 [here](https://developer.android.com/guide/topics/manifest/permission-element.html)
</br>  
  
#### PATERNS DESIGN 

* **What is a singleton class in Android?**</br>
   * A singleton class is a class which can create only an object that can be shared all other classes.
   ```
   private static volatile RESTService instance;
    protected RESTService(Context context) {
        super(context);
    }
    
    public static RESTService getInstance(Context context) {
    if (instance == null) {
       synchronized (RESTService.class) {
          if (instance == null) instance = new RESTService(context);
            }
        }
        return instance;
    }
    ```
   </br>
   

#### Displaying Lists of Content
  
* **How does RecyclerView work?**</br>
   * Let's start with some background on RecyclerView which is needed to understand ```onBindViewHolder()``` method inside RecyclerView.</br>
   * RecyclerView is designed to display long lists (or grids) of items. Say you want to display 100 rows of something. A simple approach would be to just create 100 views, one for each row and lay all of them out. But that would be wasteful because at any point of time, only 10 or so items could fit on screen and the remaining items would be off screen. So RecyclerView instead creates only the 10 or so views that are on screen. This way you get 10x better speed and memory usage. 
   * **But what happens when you start scrolling and need to start showing next views?**
     * Again a simple approach would be to create a new view for each new row that you need to show. But this way by the time you reach the end of the list you will have created 100 views and your memory usage would be the same as in the first approach. And creating views takes time, so your scrolling most probably wouldn't be smooth. This is why RecyclerView takes advantage of the fact that as you scroll, **new rows come on screen also old rows disappear off screen**. Instead of creating new view for each new row, an old view is recycled and reused by binding new data to it.
     * This happens inside the ```onBindViewHolder()``` method. Initially you will get new unused view holders and you have to fill them with data you want to display. But as you scroll you will start getting view holders that were used for rows that went off screen and you have to replace old data that they held with new data.</br>

   
* **How does RecyclerView differ from ListView?**</br>
   * **ViewHolder Pattern**:  Recyclerview implements the ViewHolders pattern whereas it is not mandatory in a ListView. A RecyclerView recycles and reuses cells when scrolling. 
   * **What is a ViewHolder Pattern?** - A ViewHolder object stores each of the component views inside the tag field of the Layout, so you can immediately access them without the need to look them up repeatedly. In ListView, the code might call ```findViewById()``` frequently during the scrolling of ListView, which can slow down performance. Even when the Adapter returns an inflated view for recycling, you still need to look up the elements and update them. A way around repeated use of ```findViewById()``` is to use the "view holder" design pattern.
   * **LayoutManager**: In a ListView, the only type of view available is the vertical ListView.  A RecyclerView decouples list from its container so we can put list items easily at run time in the different containers (linearLayout, gridLayout and staggeredLayout) by setting LayoutManager.
   * **Item Animator**: ListViews are lacking in support of good animations, but the RecyclerView brings a whole new dimension to it. Using the RecyclerView.ItemAnimator class, animating the views becomes so much easy and intuitive.
    * **Item Decoration**: In case of **ListViews**, dynamically decorating items like adding borders or dividers was never easy. But in case of **RecyclerView**, the **RecyclerView.ItemDecorator** class gives huge control to the developers but makes things a bit more time consuming and complex.</br> 
   
   
* **How would you implement swipe animation in Android**</br> 
   ```
   <set xmlns:android="http://schemas.android.com/apk/res/android"
     android:shareInterpolator="false">
    <translate android:fromXDelta="-100%" android:toXDelta="0%"
             android:fromYDelta="0%" android:toYDelta="0%"
             android:duration="700"/>
    </set>
    ```
</br>


* **What is the difference between `ListView` and `RecyclerView`?** - [Learn more here](https://stackoverflow.com/questions/26728651/recyclerview-vs-listview)

* **How does RecyclerView work internally?** - [Learn more here](https://blog.mindorks.com/how-does-recyclerview-work-internally) and [here](https://www.youtube.com/watch?v=60IYWdnHsZI)

* **What is the ViewHolder pattern? Why should we use it?** - [Learn more here](https://stackoverflow.com/questions/21501316/what-is-the-benefit-of-viewholder-pattern-in-android)

* **RecyclerView Optimization - Scrolling Performance Improvement** - [Learn more here](https://blog.mindorks.com/recyclerview-optimization)

* **What is `SnapHelper`?** - [Learn more here](https://blog.mindorks.com/using-snaphelper-in-recyclerview-fc616b6833e8)


#### Dialogs and Toasts


* **What is `Dialog` in Android?** - [Learn more here](https://developer.android.com/guide/topics/ui/dialogs)

* **What is `Toast` in Android?** 
- Android Toast can be used to display information for the short period of time. A toast contains message to be displayed quickly and disappears after sometime.
[Learn more here](https://developer.android.com/guide/topics/ui/notifiers/toasts)

* **What are Loaders in Android?**</br>
   * Loader API was introduced in API level 11 and is used to load data from a data source to display in an activity or fragment. Loaders persist and cache results across configuration changes to prevent duplicate queries.
    * Note: (Loader is Deprecated. We Have to use combination of ViewModels and LiveData instead of using Loaders) A Loader is used to fetch the data from a Content provider and cache the results across the configuration changes to avoid duplicate queries. Few implementations of Loaders like CursorLoader can implement an observer to monitor any data changes and can then trigger a reload.
       * [Sample Implementation](https://medium.com/mindorks/a-journey-to-the-world-of-mvp-and-loaders-part-2-e176200e5866) </br>
   
* **What the difference between `Dialog` and `Dialog Fragment`?** 
- A fragment that displays a dialog window, floating on top of its activity's window. This fragment contains a Dialog object, which it displays as appropriate based on the fragment's state. Dialogs are entirely dependent on Activities. If the screen is rotated, the dialog is dismissed. Dialog fragments take care of orientation, configuration changes as well. 
[Learn more here](https://stackoverflow.com/questions/7977392/android-dialogfragment-vs-dialog)

#### Intents and Broadcasting

#### INTENTS

* Describe three common use cases for using an Intent.


* **What is an intent?**</br>
  * Intents are messages that can be used to pass information to the various components of android. For instance, launch an activity, open a webview etc.</br>
  * Two types of intents-</br> 
    * Implicit: Implicit intent is when you call system default intent like send email, send SMS, dial number.</br>
    * Explicit: Explicit intent is when you call an application activity from another activity of the same application.</br>
    [Learn more here](https://blog.mindorks.com/what-are-intents-in-android) or [here](http://developer.android.com/guide/components/intents-filters.html)

* **What is an Implicit `Intent`?** - [Learn more here](https://blog.mindorks.com/what-are-intents-in-android) or [here](https://developer.android.com/guide/components/intents-filters.html#ExampleSend)
        
* **What is an Explicit `Intent`?** - [Learn more here](https://blog.mindorks.com/what-are-intents-in-android) or [here](https://developer.android.com/guide/components/intents-filters.html#ExampleExplicit)


* **What is a `BroadcastReceiver`?** - [Learn more here](https://developer.android.com/guide/components/broadcasts)

* **What is a `LocalBroadcastManager`?** - [Learn more here](https://blog.mindorks.com/using-localbroadcastmanager-in-android)

* **What is a Sticky `Intent`?**
    - Sticky Intents allows communication between a function and a service. sendStickyBroadcast() performs a sendBroadcast(Intent) known as sticky, i.e. the Intent you are sending stays around after the broadcast is complete, so that others can quickly retrieve that data through the return value of registerReceiver(BroadcastReceiver, IntentFilter). For example, if you take an intent for ACTION_BATTERY_CHANGED to get battery change events: When you call registerReceiver() for that action — even with a null BroadcastReceiver — you get the Intent that was last Broadcast for that action. Hence, you can use this to find the state of the battery without necessarily registering for all future state changes in the battery.
    <br>[Learn more here](https://stackoverflow.com/a/26038985/497132)

*   **What is the difference between START_NOT_STICKY, START_STICKY AND START_REDELIVER_INTENT?**<br/>
    A) **START_NOT_STICKY:**<br/>
    If the system kills the service after onStartCommand() returns, do not recreate the service unless there are pending intents to deliver. This is the safest option to avoid running your service when not necessary and when your application can simply restart any unfinished jobs.<br/>
    **START_STICKY:**<br/>
    If the system kills the service after onStartCommand() returns, recreate the service and call onStartCommand(), but do not redeliver the last intent. Instead, the system calls onStartCommand() with a null intent unless there are pending intents to start the service. In that case, those intents are delivered. This is suitable for media players (or similar services) that are not executing commands but are running indefinitely and waiting for a job.<br/>
    **START_REDELIVER_INTENT:**<br/>
    If the system kills the service after onStartCommand() returns, recreate the service and call onStartCommand() with the last intent that was delivered to the service. Any pending intents are delivered in turn. This is *suitable for services that are actively performing a job that should be immediately resumed, such as downloading a file.*

* **What is a Pending Intent?**</br>
* PendingIntent is a token that you give to a foreign application (e.g. NotificationManager, AlarmManager, Home Screen AppWidgetManager, or other 3rd party applications), which allows the foreign application to use your application's permissions to execute a predefined piece of code. It specifies a task that requires to be performed in future.
  * If you want someone to perform any Intent operation at future point of time on behalf of you, then we will use Pending Intent. </br>
  
* **What is an Action?**</br>
  * Description of the intent. For instance, ACTION_CALL - used to perform calls</br>

* **What is the function of an `IntentFilter`?** 
* Intent filters are a very powerful feature of the Android platform. They provide the ability to launch an activity based not only on an explicit request, but also an implicit one. For example, an explicit request might tell the system to “Start the Send Email activity in the Gmail app". By contrast, an implicit request tells the system to “Start a Send Email screen in any activity that can do the job." When the system UI asks a user which app to use in performing a task, that’s an intent filter at work. Here's an example of how to declare Intent Filter in AndroidManifest:
    ```xml
    <activity android:name=".ExampleActivity" android:icon="@drawable/app_icon">
      <intent-filter>
          <action android:name="android.intent.action.SEND" />
          <category android:name="android.intent.category.DEFAULT" />
          <data android:mimeType="text/plain" />
      </intent-filter>
    </activity>
    ```
     [Learn more here](https://developer.android.com/reference/android/content/IntentFilter)

* **Difference between Service & Intent Service**</br>
  * **Service** is the base class for Android services that can be extended to create any service. A class that directly extends Service runs on the main thread so it will block the UI (if there is one) and should therefore either be used only for short tasks or should make use of other threads for longer tasks.</br>  
  * **IntentService** is a subclass of Service that handles asynchronous requests (expressed as “Intents”) on demand. Clients send requests through startService(Intent) calls. The service is started as needed, handles each Intent in turn using a worker thread, and stops itself when it runs out of work.

    | `Service`  | `IntentService`  |
    |---|---|
    | Is invoked using `startService()`  | Is invoked using `Intent` |
    | Can be invoked from any thread  | Can in invoked from the Main thread only  |
    | Runs background operations on the Main Thread of the Application by default. Hence it can block your Application’s UI  | Creates a separate   worker thread to run background operations  |
    | Invoked multiple times would create multiple instances.  |  Invoked   multiple times won’t create multiple instances |
    | Needs to be stopped using `stopSelf()` or `stopService()`  | Automatically    stops after the queue is completed. No need to trigger `stopService()` or `stopSelf()`  |
    | Can run parallel operations  | Multiple intent calls are automatically queued and they would be executed sequentially |

</br>[Learn more here](https://stackoverflow.com/a/15772151/497132)
  

* **What are "launch modes"?** 
   * **Standard**: It creates a new instance of an activity in the task from which it was started. Multiple instances of the activity can be created and multiple instances can be added to the same or different tasks. 
     * Example: Suppose there is an activity stack of A -> B -> C. Now if we launch B again with the launch mode as “standard”, the new stack will be A -> B -> C -> B.
   * **SingleTop**: It is the same as the standard, except if there is a previous instance of the activity that exists in the top of the stack, then it will not create a new instance but rather send the intent to the existing instance of the activity. 
     * Example: Suppose there is an activity stack of A -> B. Now if we launch C with the launch mode as “singleTop”, the new stack will be A -> B -> C as usual. 
     * Now if there is an activity stack of A -> B -> C. If we launch C again with the launch mode as “singleTop”, the new stack will still be A -> B -> C.
   * **SingleTask**: A new task will always be created and a new instance will be pushed to the task as the root one. So if the activity is already in the task, the intent will be redirected to onNewIntent() else a new instance will be created. At a time only one instance of activity will exist. 
     * Example: Suppose there is an activity stack of A -> B -> C -> D. Now if we launch D with the launch mode as “singleTask”, the new stack will be A -> B -> C -> D as usual. 
     * Now if there is an activity stack of A -> B -> C -> D.  If we launch activity B again with the launch mode as “singleTask”, the new activity stack will be A -> B. Activities C and D will be destroyed.
   * **SingleInstance**: Same as single task but the system does not launch any activities in the same task as this activity. If new activities are launched, they are done so in a separate task. 
     * Eg: Suppose there is an activity stack of A -> B -> C -> D. If we launch activity B again with the launch mode as “singleTask”, the new activity stack will be: 
     * Task1 — A -> B -> C  and Task2 — D</br>
   [Learn more here](https://blog.mindorks.com/android-activity-launchmode-explained-cbc6cf996802) or
   [here](https://android.jlelse.eu/android-activity-launch-mode-e0df1aa72242)



* **Describe how broadcasts and intents work to be able to pass messages around your app?** - [Learn more here](https://stackoverflow.com/questions/7276537/using-a-broadcast-intent-broadcast-receiver-to-send-messages-from-a-service-to-a) or [here](http://www.techotopia.com/index.php/Android\_Broadcast\_Intents\_and\_Broadcast\_Receivers)


* **What are the different types of Broadcasts?** - [Learn more here](https://developer.android.com/guide/components/broadcasts)

-   **What is AAPT?**<br/>
    A) AAPT2 (Android Asset Packaging Tool) is a build tool that Android Studio and Android Gradle Plugin use to compile and package your app’s resources. AAPT2 parses, indexes, and compiles the resources into a binary format that is optimized for the Android platform.


#### Services

* **What is `Serivce`?** 
-   * A Service is an application component that can perform long-running operations in the background, and it doesn't provide a user interface. It can run in the background, even when the user is not interacting with your application. These are the three different types of services:
    * Foreground Service: A foreground service performs some operation that is noticeable to the user. For example, we can use a foreground service to play an audio track. A [Notification](https://developer.android.com/guide/topics/ui/notifiers/notifications.html) must be displayed to the user.
    * Background Service: A background service performs an operation that isn’t directly noticed by the user. In Android API level 26 and above, there are restrictions to using background services and it is recommended to use [WorkManager](https://developer.android.com/topic/libraries/architecture/workmanager) in these cases.
    * Bound Service: A service is bound when an application component binds to it by calling bindService(). A bound service offers a client-server interface that allows components to interact with the service, send requests, receive results. A bound service runs only as long as another application component is bound to it.</br> 
[Learn more here](https://developer.android.com/guide/components/services)

* **What is Service Lifecycle?** 
![image](assets/service_lifecycle.png)

* **`Service` vs `IntentService`.** 
    - IntentService is a subclass of Service that can perform tasks using worker thread unlike service that blocks main thread.
    [Learn more here](https://blog.mindorks.com/service-vs-intentservice-in-android)

      * **Difference between Activity & Service**</br>
  * Activities are basically containers or windows to the user interface. Services is a component that is used to perform operations on the background. It does not have an UI.</br>

 -  **How to Stop a Service?**<br/>
    A) To stop a service from an activity we can call stopService(Intent intent) method. To Stop a service from itself, we can call stopSelf() method.
    
-   **When does a Bound Service stops?**<br/>
    A) A Bound Service will stop automatically by the system when all the Application Components bound to it are unbinded.

-   **What is the method that differentiates it to make Service run in background?**<br/>
    A) onHandleIntent() is the method that helps the IntentService to run a particular code block declared inside it, in worker/background thread.

-   **How to Stop an IntentService?**<br/>
    A) An IntentService automatically stops itself after its job is done. We do not need to explicitly call any methods to stop an IntentService unlike Service which requires stopSelf() or StopService(intent:Intent).

-   **When Intent Service is Useful?**<br/>
    A) The IntentService can be used in long tasks usually with no communication to Main Thread. If communication is required, can use Main Thread handler or broadcast intents. Another case of use is when callbacks are needed (Intent triggered tasks).

* **What is a `JobScheduler`?** - [Learn more here](https://developer.android.com/reference/android/app/job/JobScheduler)

* **How would you update the UI of an activity from a background service**</br>
  * We need to register a LocalBroadcastReceiver in the activity. And send a broadcast with the data using intents from the background service. As long as the activity is in the foreground, the UI will be updated from the background. Ensure to unregister the broadcast receiver in the onStop() method of the activity to avoid memory leaks. 
We can also register a Handler and pass data using Handlers. I have detailed a sample implementation on this. You can check it out [here](https://medium.com/@anitaa_1990/how-to-update-an-activity-from-background-service-or-a-broadcastreceiver-6dabdb5cef74)</br>

  
* **Difference between AsyncTasks & Threads?**</br>
  * **Thread** should be used to separate long running operations from main thread so that performance is improved. But it can't be cancelled elegantly and it can't handle configuration changes of Android. You can't update UI from Thread.
  * **AsyncTask** can be used to handle work items shorter than 5ms in duration. With AsyncTask, you can update UI unlike java Thread. But many long running tasks will choke the performance.</br>
 
  
* **Difference between Service, Intent Service, AsyncTask & Threads**</br>
  * **Android service** is a component that is used to perform operations on the background such as playing music. It doesn’t has any UI (user interface). The service runs in the background indefinitely even if application is destroyed.</br>
  * **AsyncTask** allows you to perform asynchronous work on your user interface. It performs the blocking operations in a worker thread and then publishes the results on the UI thread, without requiring you to handle threads and/or handlers yourself.</br>
  * **IntentService** is a base class for Services that handle asynchronous requests (expressed as Intents) on demand. Clients send requests through startService(Intent) calls; the service is started as needed, handles each Intent in turn using a worker thread, and stops itself when it runs out of work.</br>
  * A **thread** is a single sequential flow of control within a program. Threads can be thought of as mini-processes running within a main process.</br>
   
  
* **What are Handlers?**</br>
  * Handlers are objects for managing threads. It receives messages and writes code on how to handle the message. They run outside of the activity’s lifecycle, so they need to be cleaned up properly or else you will have thread leaks.
  * Handlers allow communicating between the background thread and the main thread.
  * A Handler class is preferred when we need to perform a background task repeatedly after every x seconds/minutes.</br>
  
  
 * **What is a Job Scheduling?**</br>
   * Job Scheduling api, as the name suggests, allows to schedule jobs while letting the system optimize based on memory, power, and connectivity conditions.
   * The JobScheduler supports batch scheduling of jobs. The Android system can combine jobs so that battery consumption is reduced. JobManager makes handling uploads easier as it handles automatically the unreliability of the network. It also survives application restarts. 
   * Scenarios:
     * Tasks that should be done once the device is connect to a power supply
     * Tasks that require network access or a Wi-Fi connection.
     * Task that are not critical or user facing
     * Tasks that should be running on a regular basis as batch where the timing is not critical
     * [Reference](http://www.vogella.com/tutorials/AndroidTaskScheduling/article.html#schedulingtasks) </br>
  
  

* **What is the relationship between the life cycle of an AsyncTask and an Activity? What problems can this result in? How can these problems be avoided?**</br>
   * An AsyncTask is not tied to the life cycle of the Activity that contains it. So, for example, if you start an AsyncTask inside an Activity and the user rotates the device, the Activity will be destroyed (and a new Activity instance will be created) but the AsyncTask will not die but instead goes on living until it completes.
   * Then, when the AsyncTask does complete, rather than updating the UI of the new Activity, it updates the former instance of the Activity (i.e., the one in which it was created but that is not displayed anymore!). This can lead to an Exception (of the type java.lang.IllegalArgumentException: View not attached to window manager if you use, for instance, findViewById to retrieve a view inside the Activity).
   * There’s also the potential for this to result in a memory leak since the AsyncTask maintains a reference to the Activity, which prevents the Activity from being garbage collected as long as the AsyncTask remains alive.
   * For these reasons, using AsyncTasks for long-running background tasks is generally a bad idea . Rather, for long-running background tasks, a different mechanism (such as a service) should be employed.
   * Note: AsyncTasks by default run on a single thread using a serial executor, meaning it has only 1 thread and each task runs one after the other.</br>


* **What is the onTrimMemory() method?**</br>
   * ```onTrimMemory()```: Called when the operating system has determined that it is a good time for a process to trim unneeded memory from its process. This will happen for example when it goes in the background and there is not enough memory to keep as many background processes running as desired.
   * Android can reclaim memory for from your app in several ways or kill your app entirely if necessary to free up memory for critical tasks. To help balance the system memory and avoid the system's need to kill your app process, you can implement the ```ComponentCallbacks2``` interface in your Activity classes. The provided onTrimMemory() callback method allows your app to listen for memory related events when your app is in either the foreground or the background, and then release objects in response to app lifecycle or system events that indicate the system needs to reclaim memory. [Reference](https://developer.android.com/topic/performance/memory)</br>
  
  
* **Android Bound Service**</br>
  * A bound service is a service that allows other android components (like activity) to bind to it and send and receive data.
A bound service is a service that can be used not only by components running in the same process as local service, but activities and services, running in different processes, can bind to it and send and receive data.</br>
  * When implementing a bound service we have to extend Service class but we have to override onBind method too. This method returns an object that implements IBinder, that can be used to interact with the service.</br>
  * Implementing Android bound service with Android Messenger</br>
  * Service based on Messenger can communicate with other components in different processes, known as Inter Process Communication (IPC), without using AIDL.</br>
  * **A service handler**: this component handles incoming requests from clients that interact with the service itself.</br>
  * **A Messenger**: this class is used to create an object implementing IBinder interface so that a client can interact with the service.</br>
  * Example Implementation: [Link](https://www.survivingwithandroid.com/2014/01/android-bound-service-ipc-with-messenger-2.html)
  

* **AIDL vs Messenger Queue**</br>
  * AIDL is for purpose when you've to go application level communication for data and control sharing, a scenario depicting it can be : An app requires list of all contacts from Contacts app (content part lies here) plus it also wants to show the call's duration and you can also disconnect it from that app (control part lies here).
  * In Messenger queues you're more IN the application and working on threads and processes to manage the queue having messages so no Outside services interference here.</br>
  * Messenger is needed if you want to bind a remote service (e.g. running in another process).</br>



* **What is a ThreadPool? And is it more effective than using several separate Threads?**</br>
  * Creating and destroying threads has a high CPU usage, so when we need to perform lots of small, simple tasks concurrently, the overhead of creating our own threads can take up a significant portion of the CPU cycles and severely affect the final response time.</br>
  * ThreadPool consists of a task queue and a group of worker threads, which allows it to run multiple parallel instances of a task.</br>


* **Difference between Serializable and Parcelable?**</br>
  * Serializable is a standard Java interface. Parcelable is an Android specific interface where you implement the serialization yourself. It was created to be far more efficient than Serializable (The problem with this approach is that reflection is used and it is a slow process. This mechanism also tends to create a lot of temporary objects and cause quite a bit of garbage collection.).
  * Serialization Serialization is the process of converting an object into a stream of bytes in order to store an object into memory, so that it can be recreated at a later time, while still keeping the object's original state and data. 
  * **How to disallow serialization?** We can declare the variable as transient.</br>

Serializable uses reflection while for parcelable, developers from android team wrote custom code that performs manual marshalling(converting data into byte stream) and unmarshalling(converting the byte stream back to their original data). Usually Parcelable is considered faster than Serializable.
<br> [Learn more here](https://stackoverflow.com/a/50114007/497132)


#### Inter-process Communication

* **How can two distinct Android apps interact?** - [Learn more here](https://developer.android.com/training/basics/intents)

* **Is it possible to run an Android app in multiple processes? How?** - [Learn more here](https://stackoverflow.com/questions/6567768/how-can-an-android-application-have-more-than-one-process)

* **What is AIDL? Enumerate the steps in creating a bounded service through AIDL.** - [Learn more here](https://developer.android.com/guide/components/aidl)

* **What can you use for background processing in Android?** - [Learn more here](https://developer.android.com/guide/background)

* **What is a `ContentProvider` and what is it typically used for?** - [Learn more here](https://developer.android.com/guide/topics/providers/content-provider-basics) and [here](https://developer.android.com/guide/topics/providers/content-providers)


#### Long-running Operations

* **How to run parallel tasks in Java or Android, and get callback when all complete?** - [Learn more here](https://www.youtube.com/watch?v=v0ZSnISeyKE)

* **Why should you avoid to run non-ui code on the main thread?** - [Learn more here](https://developer.android.com/training/multiple-threads/communicate-ui)

* **What is ANR? How can the ANR be prevented?** - [Learn more here](https://developer.android.com/topic/performance/vitals/anr.html)

* **What is an `AsyncTask`?** - [Learn more here](https://www.youtube.com/watch?v=ZZ-6nGbfVdA)

* **What are the problems in AsyncTask?** - [Learn more here](https://www.youtube.com/watch?v=ZZ-6nGbfVdA)

* **When would you use java thread instead of an AsyncTask?** - [Learn more here](https://stackoverflow.com/questions/18480206/asynctask-vs-thread-in-android)

**When to use AsyncTask and when to use services?**<br/>
    A) Services are useful when you want to run code even when your application's Activity isn't open. AsyncTask is a helper class used to run some code in a separate thread and publish results in main thread. Usually AsyncTask is used for small operations and services are used for long running operations.

-    **When to use a service and when to use a thread?**<br/>
    A) We will use a Thread when we want to perform background operations when application is running in foreground. We will use a service even when the application is not running.

-   **What is a Handler?**<br/>
    A) A Handler allows you to send and process Message and Runnable objects associated with a thread's MessageQueue. Each Handler instance is associated with a single thread and that thread's message queue. When you create a new Handler, it is bound to the thread / message queue of the thread that is creating it -- from that point on, it will deliver messages and runnables to that message queue and execute them as they come out of the message queue. We will generally use handler class when we want to repeat task every few seconds.

-   **How to save password safely in Android?**<br/>
    A) Using Android Keystore<br/>
    <https://medium.com/@josiassena/using-the-android-keystore-system-to-store-sensitive-information-3a56175a454b>

-   **String a = “abc”;  String b = new String(“abc”); Will a == b ??**<br/>
    A) It depends. Here with the first statement, i.e, String a = “abc”, JVM will search for a string with “abc” in String constant pool(SCP) and if its not there it will create a new Object.
    If we wrote second statement similarly, i.e., String b = “abc”, then b will point to same string from SCP.
    However, String b = new String(“abc”) always creates a new String object.

-  **What is Alarm Manager?**<br/>
    A) AlarmManager is a class which helps scheduling your Application code to run at some point of time or at particular time intervals in future. When an alarm goes off, the Intent that had been registered for it is broadcast by the system, automatically starting the target application if it is not already running. Registered alarms are retained while the device is asleep (and can optionally wake the device up if they go off during that time), but will be cleared if it is turned off and rebooted.

-   **How can I get continuous location updates in android like in Google Maps?**<br/>
    A) We can use Fused location provider in Android set our interval in that.
    https://stackoverflow.com/a/41500910/3424919

* **What is a `Loader`? (Deprecated)** - [Learn more here](https://developer.android.com/guide/components/loaders)

* **What is the relationship between the life cycle of an `AsyncTask` and an `Activity`? What problems can this result in? How can these problems be avoided?**
    - An AsyncTask is not tied to the life cycle of the Activity that contains it. So, for example, if you start an AsyncTask inside an Activity and the user rotates the device, the Activity will be destroyed (and a new Activity instance will be created) but the AsyncTask will not die but instead goes on living until it completes.
    
    - Then, when the AsyncTask does complete, rather than updating the UI of the new Activity, it updates the former instance of the Activity (i.e., the one in which it was created but that is not displayed anymore!). This can lead to an Exception (of the type java.lang.IllegalArgumentException: View not attached to window manager if you use, for instance, findViewById to retrieve a view inside the Activity).
    
    - There’s also the potential for this to result in a memory leak since the AsyncTask maintains a reference to the Activity, which prevents the Activity from being garbage collected as long as the AsyncTask remains alive.

    - For these reasons, using AsyncTasks for long-running background tasks is generally a bad idea . Rather, for long-running background tasks, a different mechanism (such as a service) should be employed.
    
    - Note: AsyncTasks by default run on a single thread using a serial executor, meaning it has only 1 thread and each task runs one after the other.

* **Explain `Looper`, `Handler` and `HandlerThread`.** - [Learn more here](https://blog.mindorks.com/android-core-looper-handler-and-handlerthread-bd54d69fe91a) and [from video](https://www.youtube.com/watch?v=rfLMwbOKLRk&list=PL6nth5sRD25hVezlyqlBO9dafKMc5fAU2)

-   **How to handle crashing of AsyncTask during screen rotation?**<br/>
    A) The best way to handle AsyncTask crash is to create a RetainFragment, i.e., a fragment without UI as shown in the gist below: https://gist.github.com/vamsitallapudi/26030c15829d7be8118e42b1fcd0fa42
    We can also avoid this crash by using RxJava instead of AsyncTask as we will be subscribing and unsubscribing at onResume() and onPause() methods respectively.

* **How does the threading work in Android?** - [Learn more here](https://www.youtube.com/watch?v=zfDYK-xB1Uo)

* **Android Memory Leak and Garbage Collection** - [Learn more here](https://www.youtube.com/watch?v=zCSSFRRIreo)

#### Working With Multimedia Content

* **How do you handle bitmaps in Android as it takes too much memory?** - [Learn more here](https://developer.android.com/topic/performance/graphics/load-bitmap) and [here](https://developer.android.com/topic/performance/graphics/manage-memory)

* **What is the difference between a regular `Bitmap` and a nine-patch image?**
    - In general, a Nine-patch image allows resizing that can be used as background or other image size requirements for the target device. The Nine-patch refers to the way you can resize the image: 4 corners that are unscaled, 4 edges that are scaled in 1 axis, and the middle one that can be scaled into both axes.

* **Tell about the `Bitmap` pool.** - [Learn more here](https://blog.mindorks.com/how-to-use-bitmap-pool-in-android-56c71a55533c)

* **How to play sounds in Android?** - [Learn more here](https://blog.mindorks.com/using-mediaplayer-to-play-an-audio-file-in-android)

* **How image compression is preformed?** - [Learn more here](https://blog.mindorks.com/understanding-image-compression-in-android)

#### Data Saving

* **How to persist data in an Android app?** - [Learn more here](https://blog.mindorks.com/android-shared-preferences-in-kotlin)

* **What is ORM? How does it work?** - [Learn more here](https://www.youtube.com/watch?v=9OHzXUo3Ymk)

* **How would you preserve `Activity` state during a screen rotation?** - [Learn more here](https://stackoverflow.com/questions/3915952/how-to-save-state-during-orientation-change-in-android-if-the-state-is-made-of-m)

* **What are different ways to store data in your Android app?** - [Learn more here](https://blog.mindorks.com/understanding-storage-system-to-store-data-in-android) or [here](https://developer.android.com/guide/topics/data/data-storage.html)


* **Explain Scoped Storage in Android.** - [Learn more here](https://blog.mindorks.com/understanding-the-scoped-storage-in-android)

* **How to encrypt data in Android?** - [Learn more here](https://blog.mindorks.com/how-to-encrypt-data-safely-on-device-and-use-the-androidkeystore)

* **What is commit() and apply() in SharedPreferences?**
    - commit() returns a boolean value of success or failure immediately by writing data synchronously.
    - apply() is asynchronous and it won't return any boolean response. If you have an apply() outstanding and you are performing commit(), then the commit() will be blocked until the apply() is not completed.

#### Look and Feel

* **What is a `Spannable`?** - [Learn more here](https://medium.com/androiddevelopers/underspanding-spans-1b91008b97e4)

* **What is a `SpannableString`?**
   - A SpannableString has immutable text, but its span information is mutable. Use a SpannableString when your text doesn't need to be changed but the styling does. Spans are ranges over the text that include styling information like color, highlighting, italics, links, etc

* **What are the best practices for using text in Android?** - [Learn more here](https://blog.mindorks.com/best-practices-for-using-text-in-android)

* **How to implement Dark mode in any application?** - [Learn more here](https://blog.mindorks.com/implementing-dark-mode-theme-in-android)

* **How to generate dynamic colors based in image?** - [Learn more here](https://blog.mindorks.com/color-palette-in-android)

* **Explain about Density Independence Pixel** - [Learn more here](https://blog.mindorks.com/understanding-density-independent-pixel-sp-dp-dip-in-android)

#### Memory Optimizations

* **What is the `onTrimMemory()` method?** - [Learn more here](https://developer.android.com/topic/performance/memory)

* **How does the OutOfMemory happens?** - [Learn more here](https://blog.mindorks.com/practical-guide-to-solve-out-of-memory-error-in-android-application)

* **How do you find memory leaks in Android applications?** - [Learn more here](https://blog.mindorks.com/practical-guide-to-solve-out-of-memory-error-in-android-application) and [here](https://mindorks.com/blog/detecting-and-fixing-memory-leaks-in-android)

#### Android Battery Related


### 
-   **How do you reduce battery consumption?**<br/>
    A) 
    1. Never poll the server for updates.
    2. Sync only when required. Ideally, sync when phone is on Wi-Fi and plugged in.
    3. Defer your work using WorkManager.
    4. Compress your data
    5. Defer non immediate requests until the phone is plugged in or wifi is turned on. The Wi-Fi radio uses significantly less battery than the mobile radio.


-   **How do you improve battery while fetching location for an app?**<br/>
    A) 
    1. By changing Accuracy -> we can use setPriority() to PRIORITY_LOW_POWER
    2. By changing Frequency of fetching location -> we can use setInterval() to specify the time interval
    3. By increasing latency -> After our call, we can wait for longer time - we can use setMaxWaitTime() to set large timeout.


* **How to reduce battery usage in an android application?** - [Learn more here](https://blog.mindorks.com/battery-optimization-for-android-apps-f4ef6170ff70)

* **What is Doze? What about App Standby?** - [Learn more here](https://developer.android.com/training/monitoring-device-state/doze-standby)

* **What is `overdraw`?** - [Learn more here](https://developer.android.com/topic/performance/rendering/overdraw.html)

#### Supporting Different Screen Sizes

* **How do you support different types of resolutions?** - [Learn more here](https://developer.android.com/training/multiscreen/screensizes)


#### Native Programming

* **What is the NDK and why is it useful?** - [Learn more here](https://www.youtube.com/watch?v=iljxHVt7Arc) and [here](https://blog.mindorks.com/getting-started-with-android-ndk-android-tutorial) and [here](https://www.youtube.com/watch?v=iljxHVt7Arc)

* **What is renderscript?** - [Learn more here](https://blog.mindorks.com/comparing-android-ndk-and-renderscript-1a718c01f6fe)

#### Android System Internal

* **What is ABI Management?** 
    - Different Android handsets use different CPUs, which in turn support different instruction sets. Each combination of CPU and instruction sets has its own Application Binary Interface, or ABI. The ABI defines, with great precision, how an application's machine code is supposed to interact with the system at runtime. You must specify an ABI for each CPU architecture you want your app to work with. You can checkout the full specifcations <a href="https://developer.android.com/ndk/guides/abis">here</a>

* **Why bytecode cannot be run in Android?** 
    - Android uses DVM (Dalvik Virtual Machine ) rather using JVM(Java Virtual Machine).


* **What is the Dalvik Virtual Machine?** - [Learn more here](https://blog.mindorks.com/what-are-the-differences-between-dalvik-and-art)

* **What is the difference JVM, DVM and ART?** - [Learn more here](https://android.jlelse.eu/closer-look-at-android-runtime-dvm-vs-art-1dc5240c3924)

* **What are the differences between Dalvik and ART?** - [Learn more here](https://blog.mindorks.com/what-are-the-differences-between-dalvik-and-art)

* **What is DEX?** - [Learn more here](https://developer.android.com/reference/dalvik/system/DexFile)

* **Can you manually call the Garbage collector?** - [Learn more here](https://stackoverflow.com/questions/15632734/can-we-call-the-garbage-collector-explicitly)

#### Android Jetpack

* **What is Android Jetpack and why to use this?** - [Learn more here](https://blog.mindorks.com/what-is-android-jetpack-and-why-should-we-use-it)

* **What are Android Architecture Components?** 
   * A collection of libraries that help you design robust, testable, and maintainable apps. [Official documentation](https://developer.android.com/topic/libraries/architecture/)
      * **Room** - [Official documentation](https://developer.android.com/topic/libraries/architecture/room)   
        [Article on how to implement Room Db](https://medium.com/@anitaa_1990/5-steps-to-implement-room-persistence-library-in-android-47b10cd47b24)  
        [Sample  implementation](https://github.com/anitaa1990/RoomDb-Sample)
        
      * **Live Data** - [Official documentation](https://developer.android.com/topic/libraries/architecture/livedata)   
        [Sample  implementation](https://github.com/anitaa1990/GameOfThronesTrivia)
        
      * **ViewModel** - [Official documentation](https://developer.android.com/topic/libraries/architecture/viewmodel)   
        [Sample  implementation](https://github.com/anitaa1990/GameOfThronesTrivia)
        
      * **Data Binding** - [Official documentation](https://developer.android.com/topic/libraries/data-binding/)   
        [Sample  implementation](https://github.com/anitaa1990/DataBindingExample)        
        
      * **Lifecycles** - [Official documentation](https://developer.android.com/topic/libraries/architecture/lifecycle)
  </br>

[Learn more here](https://blog.mindorks.com/what-are-android-architecture-components)

* **What is LiveData in Android?** - [Learn more here](https://blog.mindorks.com/understanding-livedata-in-android)

* **How LiveData is different from ObservableField?** - [Learn more here](https://blog.mindorks.com/livedata-vs-observable-in-android)

* **What is the difference between setValue and postValue in LiveData?** - [Learn more here](https://blog.mindorks.com/livedata-setvalue-vs-postvalue-in-android)

* **How to share ViewModel between Fragments in Android?** - [Learn more here](https://blog.mindorks.com/shared-viewmodel-in-android-shared-between-fragments)

* **Explain Work Manager in Android.** - [Learn more here](https://blog.mindorks.com/integrating-work-manager-in-android)

* **Use-cases of WorkManager in Android.** - [Learn more here](https://www.youtube.com/watch?v=4LTpYXFMnJw)

* **How ViewModel work internally?** - [Learn more here](https://blog.mindorks.com/android-viewmodels-under-the-hood)


### Android Security Related
-   **How do you know if the device is rooted?**<br/>
    A) We can check if superUser apk is installed in the device or if it contains su file or xbin folder. Alternatively you can use RootBeer library available in GitHub.
    <br/>
    For code part, click [Here](https://stackoverflow.com/a/35628977/3424919).
-   **What is Symmetric Encryption?**<br/>
    A) Symmetric encryption deals with creating a passphrase and encrypting the file with it. Then the server needs to send the key to the client so that the client can decrypt. Here the problem is sending that key to decrypt the file. Hackers can easily access that key and could misuse the data.
-   **What is Asymmetric Encryption?**<br/>
    A) Using algorithms like RSA, the server generates 2 keys - public key and private key. The server then gives public key to clients. Client then encrypts the sensitive data with that public key and send it back to server. Now as the server alone has the private key, only it can decrypt the data. This is the most efficient way of sending data across the client and server.
    <br/>
    Example of this Asymmetric encryption are HTTPS using SSL certificate, Bitcoin, etc.
    For more info, refer to this [video](https://youtu.be/AQDCe585Lnc)




### Dagger 2 Related Questions:

-   **What is the use-case of @BindsInstance Annotation?**<br/>
    A) @BindsInstance is used to bind the available data at the time building the Component. Suppose I have user name available before building a component then I can use as shown in the following example:
    https://google.github.io/dagger/users-guide.html#binding-instances


-   **What is the use-case of @Module Annotation?**<br/>
    A) @Module is the Annotation used on the class for the Dagger to look inside it, to provide dependencies. We may be declaring methods inside the module class that are enclosed with @Provides annotation.

-   **What is the use-case of @Provides Annotation?**<br/>
    A) @Provides annotation is used on a method in Module class and can return / provide a Dependency object.

-   **What is the use-case of @Component Annotation?**<br/>
    A) @Component is used on Interface or abstract class. Dagger uses this interface to generate an implementation class with fully formed, dependency injected implementation, using the modules declared along with it. This generated class will be preceded by Dagger. For example if i create an interface named ProgramComponent with @Component annotation, Dagger will generate a Class named 'DaggerProgramComponent' implementing the  ProgramComponent interface.

-   **What is the use-case of @Scope Annotation?**<br/>
    A) @Scope is an annotation used on Interface to create a new Custom Scope. A Scope declaration helps to keep single instance of a class as long as its scope exists. For example, in Android, we can use @ApplicationScope for the object to live as long as the Application is live or @ActivityScope for the object to be available till the activity is killed.

-   **What is the use of Qualifier in Dagger?**<br/>
    A) We are often in a situation where we will be needing multiple objects with different instance values. For example, we need declare Student("Vamsi") and Student("Krishna"). In such case we can use a Qualifier to tell Dagger that we need multiple instances of same class. The default implementation of Qualifier is using @Named annotation, for eg., @Named("student_vamsi") and @Named("student_krishna")
    If we want to create a Custom Qualifier we would be using @Qualifier to declare a custom Qualifier interface.

-   **What is the use-case of @Inject Annotation in Dagger?**<br/>
    A) @Inject annotation is used to request dagger to provide the respective Object. We use @Inject on Constructor, Fields (mostly where constructor is not accessible like Activities, Fragments, etc.) and Methods.

### RxJava Related Questions:

More additional info to get started with RxJava is available at:
[Getting Started with RxJava2](https://www.coderefer.com/rxandroid-tutorial-getting-started/)

-   **What is an Observable in RXJava2?**<br/>
    A) An Observable  simply emits the data to those which subscribed to it. All the emission is done asynchronously to the subscribers. A simple Observable can be created as follows:

    ```java
    // RxAndroid Tutorial - Adding Observable
    Observable<String> stringObservable = Observable.just("Hello Reactive Programming!");
    ```
-   **What is an Observer in RXJava2?**<br/>
    A) Observer consumes the data emitted by the Observable. To do this, Observer needs to subscribe to the Observable. Example shows how to create an Observable in RxJava2.
    ```java
    // RxAndroid Tutorial - Adding observer
    Observer<String> stringObserver = new Observer<String>() {
            @Override
            public void onSubscribe(Disposable d) {
            }

            @Override
            public void onNext(String s) {
                Toast.makeText(MainActivity.this, s, Toast.LENGTH_SHORT).show();
            }

            @Override
            public void onError(Throwable e) {
            }

            @Override
            public void onComplete() {
            }
        };
    ```

-   **How to Subscribe / Unsubscribe in RXJava?**<br/>
    A) We can make an Observer to subscribe to Observable as follows:
    ```java
    // RxAndroid tutorial - observer subscribing to observable
    stringObservable.subscribe(stringObserver);
    ```

-   **What are the different types of Observables in RxJava?**<br/>
    A)1) single
    2) Maybe
    3) Completable
    4) Observable
    5) Flowable

-   **What is a Single in RxJava?**<br/>
    A) A Single in RxJava is an Observable which emits only one item if completed or returns error.

-   **What is Maybe in RxJava?** <br/>
    A) A Maybe in RxJava is used when the Observable needs to emit a value or a no value or an error.

-   **What is Completable in RxJava?** <br/>
    A) A Completable in RxJava is an Observable which just completes the task and does not emit anything if completed. It returns an error if anything fails.
    It is similar to reactive concept of runnable.

-   **What is Back Pressure in RxJava?**<br/>
    A) Back Pressure is the state where your observable (publisher) is creating more events than your subscriber can handle.

-   **What is Flowable in RxJava?** <br/>
    A) A Flowable in RxJava is used when the Observable emits more data than the Observer can consume. In Other words, Flowable can handle back pressure where as an Observable cannot.

-   **What is a Cold Observable?**<br/>
    A) A Cold Observable is an Observable that does not emit items until a Subscriber subscribes. If we have more than one Subscriber, then the Cold Observable will emit each sequence of items to all Subscribers one by one.

-   **What is a Hot Observable?**<br/>
    A) A Hot observable is an Observer that will emit items

-   **Hot Observables vs Cold Observables**<br/>



-   **Explain about reactive programming?**<br/>

#### Architecture

* **RXJava - What is it?**
   * [RxJava - Basics, Types of Operators, Types of Observables - Article](https://medium.com/@anitaa_1990/exploring-rxjava-in-android-e52ed7ef32e2)
   * [RxJava - Basics, Types of Operators, Types of Observables - Sample Implementation](https://github.com/anitaa1990/RxAndroid-Sample)
   
  
* **S.O.L.I.D Principles in Android development**</br>
   * [Answer](https://github.com/anitaa1990/Today-I-Learned/blob/master/android/solid_principle.md)</br>  
  
  </br></br>

#### Others

* **Arraymap/SparseArray vs HashMap in Android?**</br>
   * [Article 1 on the subject](https://android.jlelse.eu/app-optimization-with-arraymap-sparsearray-in-android-c0b7de22541a)
   * [Article 2 on the subject](https://medium.com/@mohom.r/optimising-android-app-performance-with-arraymap-9296f4a1f9eb) </br>

* **Why Bundle class is used for data passing and why cannot we use simple Map data structure?** - [Learn more here](https://developer.android.com/guide/components/activities/parcelables-and-bundles)

* **How do you troubleshoot a crashing application?** - [Learn more here](https://developer.android.com/topic/performance/vitals/crash)

* **Explain Android notification system?** - [Learn more here](https://blog.mindorks.com/how-to-increase-push-notification-delivery-rate-in-android)

* **What is the difference between Serializable and Parcelable? Which is the best approach in Android?** - [Learn more here](https://android.jlelse.eu/parcelable-vs-serializable-6a2556d51538)

* **What is AAPT?** - [Learn more here](https://developer.android.com/studio/command-line/aapt2)

* **What is the best way to update the screen periodically?** - [Learn more here](https://stackoverflow.com/questions/5452394/best-way-to-perform-an-action-periodically-while-an-app-is-running-handler)

* **FlatBuffers vs JSON.** - [Learn more here](https://blog.mindorks.com/why-consider-flatbuffer-over-json-2e4aa8d4ed07)

* **`HashMap`, `ArrayMap` and `SparseArray`** - [Learn more here](https://blog.mindorks.com/android-app-optimization-using-arraymap-and-sparsearray-f2b4e2e3dc47)

* **What are Annotations?** - [Learn more here](https://blog.mindorks.com/creating-custom-annotations-in-android-a855c5b43ed9), [Link](https://blog.mindorks.com/improve-your-android-coding-through-annotations-26b3273c137a), [and from video](https://www.youtube.com/watch?v=LEb9if2HHSw)

* **How to create custom Annotation?** - [Learn more here](https://blog.mindorks.com/creating-custom-annotations-in-android-a855c5b43ed9) and [here](https://www.youtube.com/watch?v=LEb9if2HHSw)

* **How to handle multi-touch in android?** - [Learn more here](https://developer.android.com/training/gestures/multi)

* **How to implement XML namespaces?** - [Learn more here](https://developer.android.com/reference/javax/xml/namespace/NamespaceContext)

* **What is the support library? Why was it introduced?** - [Learn more here](https://developer.android.com/topic/libraries/support-library)

* **What is Android Data Binding?** - [Learn more here](https://developer.android.com/topic/libraries/data-binding/index.html)

* **How to check if Software keyboard is visible or not?** - [Learn more here](https://blog.mindorks.com/how-to-check-the-visibility-of-software-keyboard-in-android)

* **How to take screenshot in Android programmatically?** - [Learn more here](https://blog.mindorks.com/how-to-programmatically-take-a-screenshot-on-android)

### Android Libraries

* Have you use an HTTP Library, which, why, did you like it?
* Describe how REST APIs work.
* What are some typical methods of HTTP request/responses? [[GET, POST, PUT, PATCH, DELETE, UPDATE]](http://www.restapitutorial.com/lessons/httpmethods.html)

* **Explain OkHttp Interceptor** - [Learn more here](https://blog.mindorks.com/okhttp-interceptor-making-the-most-of-it)

* **OkHttp - HTTP Caching - How caching work in Android** - [Learn more here](https://www.youtube.com/watch?v=D6dQn6pUQD0)

* **Tell me something about RxJava.** - [Learn more here](https://blog.mindorks.com/a-complete-guide-to-learn-rxjava-b55c0cea3631)

* **Advantage of Retrofit over Volley?**<br/>
    A) Retrofit is type-safe. Type safety means that the compiler will validate types while compiling, and throw an error if you try to assign the wrong type to a variable.

-   **Advantage of Volley over Retrofit?**<br/>
    A) Android Volley has a very elaborate and flexible cache mechanism. When a request is made through Volley, first the cache is checked for Response. If it is found, then it is fetched and parsed, else, it will hit Network to fetch the data. Retrofit does not support cache by default.

* **How will you handle error in RxJava?** - [Learn more here](https://blog.mindorks.com/error-handling-in-rxjava)

-   **What is the advantage of using Retrofit over AsyncTask?**<br/>
    A) Retrofit reduces boiler plate code by internally using GSON library which helps parsing the json file automatically.
    Retrofit is a type safe library. This means - it checks if wrong data type is assigned to variables at compilation time itself.
    More use-cases at: https://stackoverflow.com/a/16903205/3424919

-   **How to handle multiple network calls using Retrofit?**<br/>
      A) In Retrofit, we can call the operations asynchronously by using enqueue() method where as to call operations synchronously, we can use execute() method. In addition, we can use zip() operator from RxJava to perform multiple network calls using Retrofit library.

* **FlatMap Vs Map Operator** - [Learn more here](https://medium.com/mindorks/rxjava-operator-map-vs-flatmap-427c09678784)
    
* **When to use `Create` operator and when to use `fromCallable` operator of RxJava?** - [Learn more here](https://blog.mindorks.com/understanding-rxjava-create-and-fromcallable-operator)
    
* **When to use `defer` operator of RxJava?** - [Learn more here](https://blog.mindorks.com/understanding-rxjava-defer-operator)
    
* **How are Timer, Delay, and Interval operators used in RxJava?** - [Learn more here](https://blog.mindorks.com/understanding-rxjava-timer-delay-and-interval-operators)

* **How to make two network calls in parallel using RxJava?** - [Learn more here](https://blog.mindorks.com/understanding-rxjava-zip-operator-with-example)
    
* **Tell the difference between Concat and Merge.** - [Learn more here](https://blog.mindorks.com/rxjava-operator-concat-vs-merge)

* **Explain Subject in RxJava?** - [Learn more here](https://blog.mindorks.com/understanding-rxjava-subject-publish-replay-behavior-and-async-subject-224d663d452f)

* **What are the types of Observables in RxJava?** - [Learn more here](https://blog.mindorks.com/understanding-types-of-observables-in-rxjava-6c3a2d0819c8)

* **How to implement EventBus with RxJava?** - [Learn more here](https://blog.mindorks.com/implementing-eventbus-with-rxjava-rxbus-e6c940a94bd8)

* **How to implement search feature using RxJava in your application?** - [Learn more here](https://blog.mindorks.com/implement-search-using-rxjava-operators-c8882b64fe1d)

* **How The Android Image Loading Library Glide and Fresco Works?** - [Learn more here](https://blog.mindorks.com/how-the-android-image-loading-library-glide-and-fresco-works-962bc9d1cc40)

* **Difference between Schedulers.io() and Schedulers.computation() in RxJava.**

* **What is dependency injection?**

* **Why do we use the Dependency Injection Framework like Dagger in Android?** - [Learn more here](https://blog.mindorks.com/why-do-we-use-the-dependency-injection-framework-in-android)

* **How does the Dagger work?** - [Learn more here](https://blog.mindorks.com/android-annotation-processing-tutorial-part-1-a-practical-approach) and [here]((https://www.youtube.com/watch?v=Grzqz-B3NWU))

* **What is Component in Dagger?** - [Learn more here](https://www.youtube.com/watch?v=Grzqz-B3NWU)

* **What is Module in Dagger?** - [Learn more here](https://www.youtube.com/watch?v=Grzqz-B3NWU)

* **How does the custom scope work in Dagger?**

* **When to call dispose and clear on CompositeDisposable in RxJava?** - [Learn more here](https://stackoverflow.com/questions/47057885/when-to-call-dispose-and-clear-on-compositedisposable)

* **What is Multipart Request in Networking?** - [Learn more here](https://www.youtube.com/watch?v=p7SiNT0q1I8)

* **What is Flow in Kotlin?** - [Learn more here](https://blog.mindorks.com/what-is-flow-in-kotlin-and-how-to-use-it-in-android-project)

### Android Architecture

 **Difference between MVC & MVP & MVVM?**</br>
   * **MVC** is the Model-View-Controller architecture where model refers to the data model classes. The view refers to the xml files and the controller handles the business logic. The issue with this architecture is unit testing. The model can be easily tested since it is not tied to anything. The controller is tightly coupled with the android apis making it difficult to unit test. Modularity & flexibility is a problem since the view and the controller are tightly coupled. If we change the view, the controller logic should also be changed. Maintenance is also an issues.
   * **MVP architecture**: Model-View-Presenter architecture. The View includes the xml and the activity/fragment classes. So the activity would ideally implement a view interface making it easier for unit testing (since this will work without a view). [Sample Implementation](https://github.com/anitaa1990/Inshorts) 
   * **MVVM**: Model-View-ViewModel Architecture. The Model comprises data, tools for data processing, business logic.  The View Model is responsible for wrapping the model data and preparing the data for the view. IT also provides a hook to pass events from the view to the model.  [Sample Implementation](https://github.com/anitaa1990/Trailers)</br></br>

-   **What is the role of Presenter in MVP?**<br/>
    A) The Presenter is responsible to act as the middle man between View and Model. It retrieves data from the Model and returns it formatted to the View. But unlike the typical MVC, it also decides what happens when you interact with the View.

-   **What is the advantage of MVVM over MVP?**<br/>
    A) In MVP, Presenter is responsible for view data updates as well as data operations where as in MVVM, ViewModel does not hold any reference to View. It is the View's responsibility to pick the changes from ViewModel. This helps in writing more maintainable test cases since ViewModel does not depend upon View.

* **Describe the architecture of your last app.**

* **Describe MVP.** - [Learn more here](https://mindorks.com/course/android-mvp-introduction)

* **Describe MVVM.** - [Learn more here](https://blog.mindorks.com/mvvm-architecture-android-tutorial-for-beginners-step-by-step-guide) and [here](https://www.youtube.com/watch?v=HJMZNF-tG-4)

* **MVC vs MVP vs MVVM architecture.** - [Learn more here](https://blog.mindorks.com/mvc-mvp-mvvm-architecture-in-android)

* **What is presenter?** - [Learn more here](https://mindorks.com/course/android-mvp-introduction)

* **What is model?** - [Learn more here](https://mindorks.com/course/android-mvp-introduction)

* **Describe MVC.** - [Learn more here](https://blog.mindorks.com/mvc-mvp-mvvm-architecture-in-android)

* **Describe MVI** - [Learn more here](https://github.com/MindorksOpenSource/MVI-Architecture-Android-Beginners)

* **Describe the repository pattern** - [Learn more here](https://blog.mindorks.com/android-mvp-architecture-extension-with-interactors-and-repositories-bd4b51972339)

* **What is controller?** - [Learn more here](https://blog.mindorks.com/mvc-mvp-mvvm-architecture-in-android)

* **Tell something about clean code** - [Learn more here](https://blog.mindorks.com/every-programmer-should-read-this-book-6755dedec78d)

### Android Design Problem

* **Design Uber App.** - [Learn more here](https://github.com/MindorksOpenSource/ridesharing-uber-lyft-app)

* **Design Facebook App.**

* **Implement search functionality with debounce operator (If user keeps on typing, then cancel the last network call and hit for the present one, How will you achieve that?)**

* **Design a Location Tracking application**

* **Design Twitter.**

* **Design Bookmyshow.**

* **Design Facebook Near-By Friends App.**

* **Design WhatsApp.**

* **Design SnapChat.**

* **Design problems based on location based app.**

* **How to build offline-first app? Explain the architecture.**

* **Design LRU Cache.**

* **Design File Downloader** - [Lear from here](https://github.com/MindorksOpenSource/PRDownloader)

* **HTTP Request vs HTTP Long-Polling vs WebSockets** - [Lear from here](https://www.youtube.com/watch?v=k56H0DHqu5Y)

### Android Unit Testing
* **What is Espresso?** - [Learn more here](https://developer.android.com/training/testing/ui-testing/espresso-testing.html)

* **What is Robolectric?** - [Learn more here](http://robolectric.org/)

* **What are the disadvantages of using Robolectric?** - [Learn more here](https://stackoverflow.com/questions/18271474/robolectric-vs-android-test-framework) 

* **What is UI-Automator?** - [Learn more here](https://developer.android.com/training/testing/ui-testing/uiautomator-testing.html)

* **Explain unit test.** - [Learn more here](https://developer.android.com/training/testing/unit-testing/local-unit-tests)

* **Explain instrumented test.** - [Learn more here](https://developer.android.com/training/testing/unit-testing/instrumented-unit-tests)

* **Have you done unit testing or automatic testing?**

* **Why Mockito is used?** - [Learn more here](http://site.mockito.org/)

* **Describe JUnit test.** - [Learn more here](https://en.wikipedia.org/wiki/JUnit)

* **Describe code coverage.** - [Learn more here](https://blog.mindorks.com/generate-global-code-coverage-report-in-android-development-using-jacoco-plugin)

### Android Tools And Technologies

* Why does Android use SQLite?
* What libraries have you used for interacting with databases and why did you choose them?
* What are contract classes? [[info]](https://stackoverflow.com/a/36265603/497132)
* How do you use the BaseColumns interface to describe your data schema? [[info]](https://stackoverflow.com/a/7900591/497132)
* What is ADB?
* What is ANR?


* **What is ADB?** - [Learn more here](https://developer.android.com/studio/command-line/adb)

* **What is an Application Not Responding (ANR) error, and how can you prevent them from occurring in an app?**</br>
   * An ANR dialog appears when your UI has been unresponsive for more than 5 seconds, usually because you’ve blocked the main thread. To avoid encountering ANR errors, you should move as much work off the main thread as possible.</br>


* **Build Type, Product Flavor, Build Variant**
    * **Build Type:** Build Types controls how to build and package your app, for example whether or not ProGuard is run, how the resulting application package is signed and whether debug symbols are to be included. By default, the build system defines two build types: `debug` and `release`.
    ![](./assets/build_type.png "Build Type")
    * **Product Flavor:** Product Flavor configuration defines a customized version of the application build. It can be used to specify custom features, minimum and target API levels, device and API requirements like layout, drawable and custom code. This can help create different label apps as well. Flavours can vary in adding different features or customizing exisitng features, different icons and resources, different styles and strings etc.
    ![](./assets/product_flavor.png "Product Flavor")
    * **Build Variant:** The combination of **Build Type** and **Product Flavor** is known as **Build Variant**. For example, for above build types (debug and release) and product flavours (demo and full versions), build variants can be: `demoDebug`, `demoRelease`, `fullDebug`, `fullRelease`.


[Learn more here](https://developer.android.com/studio/build/build-variants)


* **Room vs SQLite** 
    SQLite is an in-process library that implements a self-contained, serverless, zero-configuration, transactional SQL database engine. 

    SQLite is an embedded SQL database engine. Unlike most other SQL databases, SQLite does not have a separate server process. SQLite reads and writes directly to ordinary disk files. A complete SQL database with multiple tables, indices, triggers, and views, is contained in a single disk file. The database file format is cross-platform - you can freely copy a database between 32-bit and 64-bit systems or between big-endian and little-endian architectures

    The Room persistence library provides an abstraction layer over SQLite to allow for more robust database access while harnessing the full power of SQLite.

    The library helps you create a cache of your app's data on a device that's running your app. This cache, which serves as your app's single source of truth, allows users to view a consistent copy of key information within your app, regardless of whether users have an internet connection.

    Room is an ORM, Object Relational Mapping library. In other words, Room will map our database objects to Java objects. Room provides an abstraction layer over SQLite to allow fluent database access while harnessing the full power of SQLite.

    Difference between SQLite and Room persistence library:
        - In the case of SQLite, There is no compile-time verification of raw SQLite queries. But in Room, there is SQL validation at compile time.
        - You need to use lots of boilerplate code to convert between SQL queries and Java data objects. But, Room maps our database objects to Java Object without boilerplate code.
        - As your schema changes, you need to update the affected SQL queries manually. Room solves this problem.
        - Room is built to work with LiveData and RxJava for data observation, while SQLite does not.

* **What is DDMS and what can you do with it?** - [Learn more here](https://developer.android.com/studio/profile/monitor)

* **What is the StrictMode?** - [Learn more here](https://blog.mindorks.com/use-strictmode-to-find-things-you-did-by-accident-in-android-development-4cf0e7c8d997)

* **What is Lint? What is it used for?** - [Learn more here](https://blog.mindorks.com/what-is-lint-what-is-it-used-for)

* **Git.** - [Learn more here](https://www.youtube.com/watch?v=D4h8Dbrjt4M&list=PL6nth5sRD25itbyNVUULAebzL-VLrLfkK)

* **Android Development Useful Tools.** - [Learn more here](https://blog.mindorks.com/android-development-useful-tools-fd73283e82e3)

* **Firebase.** - [Learn more here](https://firebase.google.com/)

* **How to measure method execution time in Android?** - [Learn more here](https://blog.mindorks.com/measure-method-execution-time-in-android-debug-build)

* **Can you access your database of SQLite Database for debugging?** - [Learn more here](https://blog.mindorks.com/how-to-access-sqlite-database-in-android-for-debugging)

* **What are things that we need to take care while using Proguard?** - [Learn more here](https://blog.mindorks.com/things-to-care-while-using-proguard-in-android-application)

* **What is Multidex in Android?** - [Learn more here](https://blog.mindorks.com/understanding-multidex-in-android)

* **How to use Android Studio Memory Profiler?** - [Learn more here](https://www.youtube.com/watch?v=FxDa2td6Ej8)

* **How to use Firebase realtime database in your app?** - [Learn more here](https://blog.mindorks.com/firebase-realtime-database-android-tutorial)

* **What is Gradle?** - [Learn more here](https://blog.mindorks.com/gradle-for-android-developers-getting-the-most-of-it)

* **APK Size Reduction.** 
   * Enable proguard in your project by adding following lines to your release build type.
   * Enable shrinkResources.
   * Strip down all the unused locale resources by adding required resources name in “resConfigs”.
   * Convert all the images to the webp or vector drawables.

1.  setting minifyEnabled to true
2.  setting shrinkResources to true
3.  using bundle instead of apk in developer console
4.  converting the images to vector drawables.
   * [Article on the subject](https://medium.com/exploring-code/how-you-can-decrease-application-size-by-60-in-only-5-minutes-47eff3e7874e)
   </br>
[Learn more here](https://blog.mindorks.com/how-to-reduce-apk-size-in-android-2f3713d2d662) and [here](https://blog.mindorks.com/using-r8-to-reduce-apk-size-in-android)

* **How to reduce build time of an Android app?**</br>
   * Check out this awesome [article](https://medium.com/exploring-code/how-to-decrease-your-gradle-build-time-by-65-310b572b0c43) on it. 
   * What I got from the article: A few commands we can add to the gradle.properties file:
     * ```org.gradle.configureondemand=true``` - This command will tell gradle to only build the projects that it really needs to build.
     * Use Daemon - ```org.gradle.daemon=true``` - Daemon keeps the instance of the gradle up and running in the background even after your build finishes. This will remove the time required to initialize the gradle and decrease your build timing significantly.
     * ```org.gradle.parallel=true``` - Allow gradle to build your project in parallel. If you have multiple modules in you project, then by enabling this, gradle can run build operations for independent modules parallelly.
     * Increase Heap Size - ```org.gradle.jvmargs=-Xmx3072m -XX:MaxPermSize=512m -XX:+HeapDumpOnOutOfMemoryError -Dfile.encoding=UTF-8``` - Since android studio 2.0, gradle uses dex in the process to decrease the build timings for the project. Generally, while building the applications, multiple dx processes runs on different VM instances. But starting from the Android Studio 2.0, all these dx processes runs in the single VM and that VM is also shared with the gradle. This decreases the build time significantly as all the dex process runs on the same VM instances. But this requires larger memory to accommodate all the dex processes and gradle. That means you need to increase the heap size required by the gradle daemon. By default, the heap size for the daemon is about 1GB. 
  * Ensure that dynamic dependency is not used. i.e. do not use 
  </br>```implementation 'com.android.support:appcompat-v7:27.0.+'```. </br>
  This command means gradle will go online and check for the latest version every time it builds the app.</br> 
  Instead use fixed versions i.e. ```'com.android.support:appcompat-v7:27.0.2'```    
   </br>

* **How can you speed up the Gradle build?** - [Learn more here](https://blog.mindorks.com/speed-up-gradle-build-for-android-to-save-your-time)

* **What is a BuildType in Gradle? And what can you use it for?** 
    - Build types define properties that Gradle uses when building and packaging your Android app.
    - A build type defines how a module is built, for example whether ProGuard is run.
    - A product flavor defines what is built, such as which resources are included in the build.
    - Gradle creates a build variant for every possible combination of your project’s product flavors and build types.

* **How can you speed up the Gradle build?** - [Learn more here](https://blog.mindorks.com/speed-up-gradle-build-for-android-to-save-your-time)

* **Explain the build process in Android:** 
    - First step involves compiling the resources folder (/res) using the aapt (android asset packaging tool) tool. These are compiled to a single class file called R.java. This is a class that just contains constants.
    - Second step involves the java source code being compiled to .class files by javac, and then the class files are converted to Dalvik bytecode by the "dx" tool, which is included in the sdk 'tools'. The output is classes.dex.
    - The final step involves the android apkbuilder which takes all the input and builds the apk (android packaging key) file.

* **About multiple apk for android application.** - [Learn more here](https://mindorks.com/blog/how-to-create-multiple-apk-files-for-android-application)

* **What is proguard used for?** - [Learn more here](https://blog.mindorks.com/applying-proguard-in-an-android-application)

* **What is obfuscation? What is it used for? What about minification?** - [Learn more here](https://www.youtube.com/watch?v=yduedsaxfDw)

* **How to change some parameters in an app without app update?** - [Learn more here](https://blog.mindorks.com/getting-started-with-firebase-remote-config-in-android)




