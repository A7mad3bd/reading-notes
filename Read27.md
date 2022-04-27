# Read 27
# Tasks and the back stack


## What are Tasks and Back Stacks?

- A task is a stack of activities.
- These activities are arranged in a stack -- the back stack -- in the order in which each activity is opened.


## Lifcycle

- When act A starts Act B, Act A is stopped, but the system retains its state. If the user uses the back or gesture while in activity b, act a resumes with its state restored.
- If the user presses or gestures Back, the current activity is popped from the stack and destroyed.
- Activities can be instantiated multiple times, even from other tasks.

## Manage Tasks

- The way android manages tasks and the back stack is by placing all activities started in succession in the same task and in a last-in, first-out stack. You can modify these within the manifest.

## Handle Affinities

- These indicate which task an activity prefers to belong to.

## Shared Preferences

- If you have a small collection of key values that you'd like to save, you should use the `sharedPreferences` APIs.
- Each file is managed by the framework and can be private or shared.
- The SharedPreferences APIs are for reading and writing key-value pairs, and you should not confuse them with the Preference APIs, which help you build a user interface for your app settings

### Sace key-value data

- SharedPerferences APIs are for key values that you want to save

#### Get Handle to shared preferences
````Java
Context context = getActivity();
SharedPreferences sharedPref = context.getSharedPreferences(
        getString(R.string.preference_file_key), Context.MODE_PRIVATE);

//alt

        SharedPreferences sharedPref = getActivity().getPreferences(Context.MODE_PRIVATE);
````


#### Write to shared preferences
````Java
SharedPreferences sharedPref = getActivity().getPreferences(Context.MODE_PRIVATE);
SharedPreferences.Editor editor = sharedPref.edit();
editor.putInt(getString(R.string.saved_high_score_key), newHighScore);
editor.apply();
````


#### Read from shared preferences
````Java
SharedPreferences sharedPref = getActivity().getPreferences(Context.MODE_PRIVATE);
int defaultValue = getResources().getInteger(R.integer.saved_high_score_default_key);
int highScore = sharedPref.getInt(getString(R.string.saved_high_score_key), defaultValue);
````


## Resources

- [Tasks and the back stack](https://developer.android.com/guide/components/activities/tasks-and-back-stack)
- [Shared Preferences](https://developer.android.com/training/data-storage/shared-preferences)