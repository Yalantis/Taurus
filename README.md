# Pull-to-Refresh.Tours
[![Yalantis](https://raw.githubusercontent.com/Yalantis/Taurus/master/badge_dark.png)](https://yalantis.com/?utm_source=github)

This project aims to provide a simple and customizable pull to refresh implementation.

Check this [project on Behance] (https://www.behance.net/gallery/20411445/Mobile-Animations-Interactions)  
Check this [project on Dribbble] (https://dribbble.com/shots/1623131-Pull-to-Refresh)

<img src="https://d13yacurqjgara.cloudfront.net/users/125056/screenshots/1623131/tours-pull-airplane_2-2-3.gif" alt="alt text" style="width:200;height:200">

[Sample APK] (https://github.com/Yalantis/Taurus/blob/develop/sample-taurus.apk?raw=true)

#Usage

*For a working implementation, Have a look at the Sample Project - sample*

1. Include the library as local library project.

2. Include the PullToRefreshView widget in your layout.

	```xml
    <com.yalantis.taurus.PullToRefreshView
        android:id="@+id/pull_to_refresh"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:type="sun">

        <ListView
            android:id="@+id/list_view"
            android:divider="@null"
            android:dividerHeight="0dp"
            android:layout_width="match_parent"
            android:layout_height="match_parent" />

    </com.yalantis.taurus.PullToRefreshView>
    ```

3. In your `onCreate` method refer to the View and setup OnRefreshListener.
	```java
    mPullToRefreshView = (PullToRefreshView) findViewById(R.id.pull_to_refresh);
    mPullToRefreshView.setOnRefreshListener(new PullToRefreshView.OnRefreshListener() {
        @Override
        public void onRefresh() {
            mPullToRefreshView.postDelayed(new Runnable() {
                @Override
                public void run() {
                    mPullToRefreshView.setRefreshing(false);
                }
            }, REFRESH_DELAY);
        }
     });
     ```

# Misc
If you need to change progress state:
```java
	mPullToRefreshView.setRefreshing(boolean isRefreshing)
```

##Installing with [Gradle](http://gradle.org/)
```groovy
implementation 'com.github.yalantis:taurus:1.0.3'
```

#Compatibility
  
  * Android HONEYCOMB 3.0+
  
# Changelog

### Version: 1.0.3

  * Updated depdendencies
  * Migrated to AndroidX

### Version: 1.0.2

  * Updated gradle version

### Version: 1.0

  * Initial Build
  

#### Let us know!

We’d be really happy if you sent us links to your projects where you use our component. Just send an email to github@yalantis.com And do let us know if you have any questions or suggestion regarding the animation. 

P.S. We’re going to publish more awesomeness wrapped in code and a tutorial on how to make UI for Android (iOS) better than better. Stay tuned!

## License

    Copyright 2017, Yalantis

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
