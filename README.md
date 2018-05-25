# AndroidPageIndicator
Android 页面指示器。

### 本应用的示例

![image](https://github.com/iWay7/AndroidPageIndicator/blob/master/sample.gif)   

### 本示例基于 AndroidHelpers 库，访问 https://github.com/iWay7/AndroidHelpers 添加依赖。

#### 开始使用：
##### 在布局文件中声明一个 PageIndicator 视图：
```
<site.iway.androidhelpers.PageIndicator
    android:id="@+id/pageIndicator"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_gravity="bottom|center_horizontal"
    android:layout_marginBottom="50dp"
    app:indicatorSpacing="5dp"
    app:pageCount="3"
    app:pageIndex="0"/>
```

##### 其中的属性如下：
```
app:indicatorSpacing // 指示点的间距
app:pageCount // 指示点的数量
app:pageIndex // 当前指示的位置
app:resSelected // 选中的 Drawable
app:resUnselected // 未选中的 Drawable
```

##### 使用代码控制指示器的位置：
```
pageIndicator.setPageIndex(...);
```

##### 可以用下方式绑定到 ViewPager 中：
```
viewPager.setOnPageChangeListener(new OnPageChangeListener() {
    @Override
    public void onPageScrolled(int position, float positionOffset, int positionOffsetPixels) {
    }
    
    @Override
    public void onPageSelected(int position) {
        pageIndicator.setPageIndex(position);
    }
    
    @Override
    public void onPageScrollStateChanged(int state) {
    }
});
```