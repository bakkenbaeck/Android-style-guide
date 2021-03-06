# Android Style Guide

The intention of this guide is to provide a set of conventions that encourage good code that is specific to the Android environment.

## In General

You should strive to make code that is **easy to read**, **easy to understand**, and **easy to maintain**. That is why it is important when reviewing code to ensure these guidelines are met no matter how small, or nit-picky a request for a change may seem.

## Naming

#### Class Files

Any classes extending an Android framework component should **always** end with the component name. For example:

	UserFragment, SignUpActivity, RateAppDialog, PushNotificationServer, NumberView

#### Resource files

When naming resource files you should be sure to name them using lowercase letters and underscores instead of spaces, for example:

	activity_main, fragment_user, item_post

#### View IDs

When giving views IDs you should name them using camel case pattern. This is because it is now trivial to bind views in code.

	android:id="@+id/launchButton", android:id="@+id/newItemButton"

#### Drawable files

Drawable resource files should be named using the **ic_** prefix along with the size and color of the asset. For example, white accept icon sized at 24dp would be named:

	ic_accept_24dp_white

And a black cancel icon sized at 48dp would be named:

	ic_cancel_48dp_black

We use this naming convention so that a drawable file is recognisable by its name. If the colour and size are not stated in the name, then the developer needs to open the drawable file to find out this information.

Other drawable files should be named using the corresponding prefix, for example:

| Type       | Prefix    | Example                |
|------------|-----------|------------------------|
| Selector   | selector_ | selector_button_cancel |
| Background | bg_       | bg_rounded_button      |
| Circle     | circle_   | circle_white           |
| Progress   | progress_ | progress_circle_purple |
| Divider    | divider_  | divider_grey           |

When creating selector state resources, they should be named using the corresponding suffix:

| State    | Suffix    | Example             |
|----------|-----------|---------------------|
| Normal   | _normal   | btn_accept_normal   |
| Pressed  | _pressed  | btn_accept_pressed  |
| Focused  | _focused  | btn_accept_focused  |
| Disabled | _disabled | btn_accept_disabled |
| Selected | _selected | btn_accept_selected |


#### Layout files

When naming layout files, they should be named starting with the name of the Android Component that they have been created for. For example:

| Component        | Class Name      | Layout Name       |
|------------------|-----------------|-------------------|
| Activity         | MainActivity    | activity_main     |
| Fragment         | MainFragment    | fragment_main     |
| Dialog           | RateDialog      | dialog_rate       |
| Widget           | UserProfileView | view_user_profile |
| AdapterView Item | N/A             | item_follower     |

**Note:** If you create a layout using the merge tag then the layout_ prefix should be used.

## Best practices

#### Layout/view setup

    // Good
    <TextView
        android:id="@+id/label"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="right"
        android:textSize="14sp"
        android:textColor="#000"
        android:text="John Doe"/>

    // Bad
    <TextView
        android:textSize="14sp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="John Doe"
        android:id="@+id/label"
        android:layout_gravity="right"
        android:textColor="#000" />

1. ID should always be first
2. height/width
3. Alignment(gravity/orientation)
4. Styles(style/textColor/textSize/backgroundColor etc)
5. Text should always be last
