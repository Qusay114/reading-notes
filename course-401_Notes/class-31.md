# Espresso :

use Espresso to write concise, beautiful, and reliable Android UI tests. 

Example : 

        @Test
        public void greeterSaysHello() {
            onView(withId(R.id.name_field)).perform(typeText("Steve"));
            onView(withId(R.id.greet_button)).perform(click());
            onView(withText("Hello Steve!")).check(matches(isDisplayed()));
        }



Espresso tests run optimally fast! It lets you leave your waits, syncs, sleeps, and polls behind while it manipulates and asserts on the application UI when it is at rest , the target audience are the developers .
Each time your test invokes onView(), Espresso waits to perform the corresponding UI action or assertion until the following synchronization conditions are met:

The message queue is empty.
There are no instances of AsyncTask currently executing a task.
All developer-defined idling resources are idle.
By performing these checks, Espresso substantially increases the likelihood that only one UI action or assertion can occur at any given time. This capability gives you more reliable and dependable test results.

Packages : 

espresso-core
espresso-web
espresso-idling-resource
espresso-contrib
espresso-intents
espresso-remote


# Create UI tests with Espresso Test Recorder :

you can create UI tests for your app without writing any codes and that by using The Espresso Test Recorder tool lets you create UI

to create your test , you need to simulate your UI to do the actions , like typing a text in the input field , press on a button and finaly check on it (same as assertions) :

Example : 

        @Test
            public void ensureTextChangesWork() {
                // Type text and then press the button.
                onView(withId(R.id.inputField))
                        .perform(typeText("HELLO"), closeSoftKeyboard());
                onView(withId(R.id.changeText)).perform(click());

                // Check that the text was changed.
                onView(withId(R.id.inputField)).check(matches(withText("Lalala")));
            }

            @Test
            public void changeText_newActivity() {
                // Type text and then press the button.
                onView(withId(R.id.inputField)).perform(typeText("NewText"),
                        closeSoftKeyboard());
                onView(withId(R.id.switchActivity)).perform(click());

                // This view is in a different Activity, no need to tell Espresso.
                onView(withId(R.id.resultView)).check(matches(withText("NewText")));
            }
        }


![espresso](https://saucelabs.com/sauce-labs/images/espresso-test4.jpg)
