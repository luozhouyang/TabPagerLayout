# TabPagerLayout
A View based on ViewPager and TabLayout.


## Demo  

<img src="art/TabPagerLayout.gif" width="320px" />

## Attrs

```
    <declare-styleable name="TabPagerLayout">
        <attr name="backgroundColor" format="color" />
        <attr name="tabTextSize" format="dimension" />
        <attr name="tabHeight" format="dimension" />
        <attr name="tabNormalTextColor" format="color"/>
        <attr name="tabSelectedTextColor" format="color"/>
        <attr name="tabIndicatorColor" format="color"/>
        <attr name="tabIndicatorHeight" format="dimension"/>
        <attr name="toolbarShowUp" format="boolean" />
        <attr name="toolbarTitle" format="string"/>
        <attr name="toolbarTitleColor" format="color"/>
    </declare-styleable>
```  


## Usage  

* Gradle  
Add repository in your root build.gradle file:  
```gradle  
allprojects {
    repositories {
        jcenter()
        maven { url 'https://jitpack.io' }
    }
}

```  

Add dependency in your module level build.gradle file:  
```gradle  
compile 'com.github.StupidL:tabpagerlayout:0.1.0'  
```  


* Add TabPagerLayout in your xml files.  

```xml  
<?xml version="1.0" encoding="utf-8"?>
<me.stupidme.tabpagerlayout.TabPagerLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/tab_pager_layout"
    android:layout_width="match_parent"
    android:layout_height="match_parent" />

```  

* Find view in your activity:


```java  

    TabPagerLayout tabPagerLayout = (TabPagerLayout) findViewById(R.id.tab_pager_layout);

    List<TabItem> items = new ArrayList<>();

    for (int i = 0; i < 8; i++) {
        TabItem item = new TabItem();
        item.setTabTitle("TAB" + i);
        item.setTabColor(getResources().getColor(mColors[i]));
        Fragment fragment = BlankFragment.newInstance(i + "");
        item.setTabFragment(fragment);
        items.add(item);
    }

    tabPagerLayout.addAllTabItems(items)
            .setToolbarTitle("TabPagerLayout")
            .setTabHeight(56)
            .setTabIndicatorColor(Color.WHITE)
            .setTabIndicatorHeight(8)
            .setTabNormalTextColor(Color.WHITE)
            .setTabSelectedTextColor(Color.BLACK)
            .showToolbarUp(true)
            .setTabPagerLayoutListener(new TabPagerLayout.TabPagerLayoutListener() {
                @Override
                public void setToolbarUpOnClickListener(ActionBar actionBar) {
                    //...
                }
            });
                
```  


## License

```bash  

Copyright 2017 StupidL

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

```  



