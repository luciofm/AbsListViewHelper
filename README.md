# AbsListViewHelper

Really simple attacher class to add a header and/or a footer to an Android AbsListView

### Demo

### Usage

In your ``build.gradle`` file:

```groovy
repositories {
    maven { url 'https://github.com/felipecsl/m2repository/raw/master/' }
    // ...
}

dependencies {
    // ...
    compile 'com.felipecsl:abslistviewhelper:1.0.+'
}
```

In your activity class:

```java
private ListView listView;
private ArrayAdapter<String> adapter;

@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);

    setContentView(R.layout.activity_main);

    GridView gridView = (GridView) findViewById(R.id.gridView);
    View gridHeader = findViewById(R.id.gridHeader);
    View gridFooter = findViewById(R.id.gridFooter);

    // Initialize your adapter the way you want...
    ListAdapter myAdapter = new MyAdapter();

    gridView.setAdapter(myAdapter);

    AbsListViewHelper helper = new AbsListViewHelper(gridView)
            .setHeaderView(gridHeader)
            .setFooterView(gridFooter);

    // If you want to set an OnScrollListener on the GridView,
    // you have to call it on the helper instance. See below:
    helper.registerOnScrollListener(scrollListener);

    // that's it!
}
```

Check the [sample app](https://github.com/felipecsl/AbsListViewHelper/blob/master/app/src/main/java/com/felipecsl/abslistviewhelper/app/MainActivity.java) for an example of usage.

Works with API Level 10 and above.

### Changelog

Please see the [Changelog](https://github.com/felipecsl/AbsListViewHelper/blob/master/CHANGELOG.md) to check what's recently changed.

### Contributing

* Check out the latest master to make sure the feature hasn't been implemented or the bug hasn't been fixed yet
* Check out the issue tracker to make sure someone already hasn't requested it and/or contributed it
* Fork the project
* Start a feature/bugfix branch
* Commit and push until you are happy with your contribution
* Make sure to add tests for it. This is important so I don't break it in a future version unintentionally.

### Copyright and license

Code and documentation copyright 2011-2014 Felipe Lima.
Code released under the [MIT license](https://github.com/felipecsl/QuickReturn/blob/master/LICENSE.txt).
