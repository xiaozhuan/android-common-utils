# android-common-utils
this is a common utils of android (used to fast develop). contains QuickAdapter of ListView,RecyclerView.ExpandListView. and so on.

 <img src="/images/swipe_adapter_1.gif" alt="Demo Screen Capture" width="300px" />

## New Features

  
## fast adapter sample code 
``` java
   mRecyclerView_room.setAdapter(mRoomAdapter = new QuickRecycleViewAdapter<RoomItem>(
                        R.layout.item_ktv_detail_room, dateItems) {
                    @Override
                    protected void onBindData(Context ctx, final int position, final RoomItem roomItem, ViewHelper helper) {
                        if (roomItem.isSelected()) {
                            helper.setBackgroundRes(R.id.fl_room, mRoomSelectDrawableId)
                                    .setTextColor(R.id.tv_room_title, mRoomSelectedColor)
                                    .setVisibility(R.id.iv_room_subscript, true);
                        } else {
                            helper.setBackgroundRes(R.id.fl_room, 0)
                                    .setTextColor(R.id.tv_room_title, mRoomUnselectColor)
                                    .setVisibility(R.id.iv_room_subscript, false);
                        }
                        helper.setText(R.id.tv_room_title, roomItem.text)
                                .setOnClickListener(R.id.fl_room, new View.OnClickListener() {
                                    public void onClick(View v) {
                                        if (getSelectedPosition() != position) {
                                            setRoomFragment(roomItem.roomInfos);
                                        }
                                        setSelected(position);
                                    }
                                });
                    }
                }
        );
```

## How to use ? 

common-util (已包含volley扩展库：volley_with_extra)
``` java
dependencies {
     compile 'org.heaven7.core:commonutil:1.8.2'
}
```
view lib -> common-view

``` java
dependencies {
     compile 'org.heaven7.core.view:common-view:1.0.0'
}
```

volley及其扩展库
expand volley lib - > volley_with_extra
``` java
dependencies {
    compile 'com.heaven7.volley:volley_with_extra:1.0.1'
}
```

第三方sdk,目前已集成 支付宝，微信支付。 qq，微信登陆，分享
third sdk lib - > third_sdks 

``` java
dependencies {
    compile 'com.heaven7.third_sdks:third_sdks:1.0.3'
}
```

## thanks
 szpnygo's [SwipeRecyclerView](https://github.com/szpnygo/android-SwipeRecyclerView)

## License

    Copyright 2015   
                    heaven7(donshine723@gmail.com)

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
