# 2022年夏季《移动软件开发》实验报告



<center>姓名：姜景达  学号：20020007022</center>

| 姓名和学号？         | 姜景达，20020007022              |
| -------------------- | -------------------------------- |
| 本实验属于哪门课程？ | 中国海洋大学22夏《移动软件开发》 |
| 实验名称？           | 实验6：安卓APP首页构建           |
| 博客地址？           | XXXXXXX                          |
| Github仓库地址？     | XXXXXXX                          |

（备注：将实验报告发布在博客、代码公开至 github 是 **加分项**，不是必须做的）



## **一、实验目标**

做一个APP首页，包括顶部图片、顶部菜单栏、中部消息模块、底部Tab按钮。学习 ScrollView, RelativeLayout，以及插件之间的穿插使用。

## 二、实验步骤

activity_main.xml代码：

``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:orientation="horizontal"
    android:layout_height="match_parent">

    <ScrollView
        android:layout_width="match_parent"
        android:layout_height="match_parent">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:orientation="vertical">

            <TextView
                android:layout_width="match_parent"
                android:layout_height="50dp"
                android:gravity="center"
                android:text="首页"
                android:textColor="#333"
                android:textSize="18dp"
                android:textStyle="bold" />

            <ImageView
                android:layout_width="match_parent"
                android:layout_height="200dp"
                android:layout_marginLeft="10dp"
                android:layout_marginRight="10dp"
                android:src="@mipmap/test_img" />

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginLeft="10dp"
                android:layout_marginRight="10dp"
                android:orientation="horizontal"
                android:weightSum="4">

                <LinearLayout
                    android:layout_width="0dp"
                    android:layout_height="100dp"
                    android:layout_weight="1"
                    android:orientation="vertical">

                    <ImageView
                        android:layout_width="50dp"
                        android:layout_height="50dp"
                        android:layout_gravity="center_horizontal"
                        android:layout_marginTop="10dp"
                        android:background="@mipmap/test_icon1" />

                    <TextView
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:layout_marginTop="10dp"
                        android:gravity="center"
                        android:text="验房" />
                </LinearLayout>

                <LinearLayout
                    android:layout_width="0dp"
                    android:layout_height="100dp"
                    android:layout_weight="1"
                    android:orientation="vertical">

                    <ImageView
                        android:layout_width="50dp"
                        android:layout_height="50dp"
                        android:layout_gravity="center_horizontal"
                        android:layout_marginTop="10dp"
                        android:background="@mipmap/test_icon2" />

                    <TextView
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:layout_marginTop="10dp"
                        android:gravity="center"
                        android:text="日常巡检" />
                </LinearLayout>

                <LinearLayout
                    android:layout_width="0dp"
                    android:layout_height="100dp"
                    android:layout_weight="1"
                    android:orientation="vertical">

                    <ImageView
                        android:layout_width="50dp"
                        android:layout_height="50dp"
                        android:layout_gravity="center_horizontal"
                        android:layout_marginTop="10dp"
                        android:background="@mipmap/key" />

                    <TextView
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:layout_marginTop="10dp"
                        android:gravity="center"
                        android:text="钥匙管理" />
                </LinearLayout>

                <LinearLayout
                    android:layout_width="0dp"
                    android:layout_height="100dp"
                    android:layout_weight="1"
                    android:orientation="vertical">

                    <ImageView
                        android:layout_width="50dp"
                        android:layout_height="50dp"
                        android:layout_gravity="center_horizontal"
                        android:layout_marginTop="10dp"
                        android:background="@mipmap/tongji" />

                    <TextView
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:layout_marginTop="10dp"
                        android:gravity="center"
                        android:text="统计分析" />
                </LinearLayout>
            </LinearLayout>

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginTop="20dp"
                android:orientation="horizontal">

                <TextView
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_marginLeft="10dp"
                    android:layout_weight="1"
                    android:text="待办（10）"
                    android:textColor="#333"
                    android:textSize="16dp"
                    android:textStyle="bold" />

                <TextView
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_marginLeft="10dp"
                    android:layout_marginRight="10dp"
                    android:text="更多"
                    android:textColor="#666" />
            </LinearLayout>

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="80dp"
                android:layout_marginLeft="10dp"
                android:layout_marginTop="20dp"
                android:layout_marginRight="10dp"
                android:orientation="horizontal">

                <ImageView
                    android:layout_width="match_parent"
                    android:layout_height="80dp"
                    android:background="@mipmap/img" />
            </LinearLayout>

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="80dp"
                android:layout_marginLeft="10dp"
                android:layout_marginTop="20dp"
                android:layout_marginRight="10dp"
                android:orientation="horizontal">

                <ImageView
                    android:layout_width="match_parent"
                    android:layout_height="80dp"
                    android:background="@mipmap/img_1" />
            </LinearLayout>

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="80dp"
                android:layout_marginTop="250dp"
                android:weightSum="4">

                <RelativeLayout
                    android:layout_width="0dp"
                    android:layout_height="match_parent"
                    android:layout_weight="1">

                    <ImageView
                        android:id="@+id/img1"
                        android:layout_width="30dp"
                        android:layout_height="30dp"
                        android:layout_centerHorizontal="true"
                        android:layout_marginTop="15dp"
                        android:background="@mipmap/test_icon3" />

                    <TextView
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:layout_below="@+id/img1"
                        android:layout_centerHorizontal="true"
                        android:layout_marginTop="5dp"
                        android:gravity="center"
                        android:text="首页" />

                </RelativeLayout>

                <RelativeLayout
                    android:layout_width="0dp"
                    android:layout_height="match_parent"
                    android:layout_weight="1">

                    <ImageView
                        android:id="@+id/img2"
                        android:layout_width="30dp"
                        android:layout_height="30dp"
                        android:layout_centerHorizontal="true"
                        android:layout_marginTop="15dp"
                        android:background="@mipmap/icon12" />

                    <TextView
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:layout_below="@+id/img2"
                        android:layout_marginTop="4dp"
                        android:gravity="center"
                        android:text="验房" />

                </RelativeLayout>

                <RelativeLayout
                    android:layout_width="0dp"
                    android:layout_height="match_parent"
                    android:layout_weight="1">

                    <ImageView
                        android:id="@+id/img3"
                        android:layout_width="30dp"
                        android:layout_height="30dp"
                        android:layout_centerHorizontal="true"
                        android:layout_marginTop="15dp"
                        android:background="@mipmap/icon13" />

                    <TextView
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:layout_below="@+id/img3"
                        android:layout_centerHorizontal="true"
                        android:layout_marginTop="5dp"
                        android:gravity="center"
                        android:text="统计" />

                </RelativeLayout>

                <RelativeLayout
                    android:layout_width="0dp"
                    android:layout_height="match_parent"
                    android:layout_weight="1">

                    <ImageView
                        android:id="@+id/img4"
                        android:layout_width="30dp"
                        android:layout_height="30dp"
                        android:layout_centerHorizontal="true"
                        android:layout_marginTop="15dp"
                        android:background="@mipmap/icon14" />

                    <TextView
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:layout_below="@+id/img4"
                        android:layout_centerHorizontal="true"
                        android:layout_marginTop="5dp"
                        android:gravity="center"
                        android:text="设置" />

                </RelativeLayout>
            </LinearLayout>
        </LinearLayout>
    </ScrollView>
</LinearLayout>
```





## 三、程序运行结果

![image-20220826183656000](C:\Users\姜景达\AppData\Roaming\Typora\typora-user-images\image-20220826183656000.png)



## 四、问题总结与体会

学习了 ScrollView, RelativeLayout，以及插件之间的穿插使用