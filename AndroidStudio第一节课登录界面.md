# AndroidStudio第一节课登录界面

[TOC]

## 1安装启动AndroidStudio

## 2登录界面

### 2.1 新建LoginActivity

![](E:\Desktop\TIM截图20200220165904.jpg)

layout对应会出现activity_login_activtiy.xml

### 2.2 创建界面

创建后，打开layout对应的xml修改为RelativeLayout

![](E:\Desktop\TIM截图20200220170142.jpg)

打开Design模式，选取框体

`TextView`(文本框)，是`Android`中用于显示文本的一个控件

Button是一种比较常用的控件爱你，最常用的就是其监听事件

![](E:\Desktop\TIM截图20200220182344.jpg)

我们也可以在Text模式中进行设计

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.test01.LoginActivity">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentTop="true"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="45dp"
        android:text="登 录 界 面"      //显示的内容
        android:textSize="25dp"       //字体大小
        android:textColor="#FF7300"/> //颜色

    <TextView
        android:id="@+id/textView2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="20dp"
        android:text="用户名："
        android:layout_alignBaseline="@+id/editText"
        android:layout_alignBottom="@+id/editText"
        android:layout_toStartOf="@+id/textView"
        android:layout_marginEnd="11dp" />

    <TextView
        android:id="@+id/textView3"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="20dp"
        android:text="密码："
        android:layout_alignBaseline="@+id/editText2"
        android:layout_alignBottom="@+id/editText2"
        android:layout_alignStart="@+id/textView2" />

    <EditText
        android:id="@+id/editText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/textView"
        android:layout_marginStart="22dp"
        android:layout_marginTop="46dp"
        android:layout_toEndOf="@+id/textView2"
        android:ems="10"
        android:inputType="textPersonName"
        android:hint="请输入用户名" />

    <EditText
        android:id="@+id/editText2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignStart="@+id/editText"
        android:layout_below="@+id/editText"
        android:layout_marginTop="23dp"
        android:ems="10"
        android:hint="请输入密码"
        android:inputType="textPassword" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentBottom="true"
        android:layout_alignStart="@+id/textView3"
        android:layout_marginBottom="26dp"
        android:text="确 定" />

    <Button
        android:id="@+id/button2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignBottom="@+id/button"
        android:layout_alignEnd="@+id/editText2"
        android:text="退 出" />

    <TextView
        android:id="@+id/textView4"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="点击我进行注册"
        android:layout_below="@+id/editText2"
        android:layout_marginTop="89dp"
        android:layout_toEndOf="@+id/button" />

    <TextView
        android:id="@+id/textView5"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/textView4"
        android:layout_marginTop="33dp"
        android:text="点击联系我们"
        android:layout_alignEnd="@+id/textView4"
        android:layout_alignStart="@+id/editText2" />
</RelativeLayout>
```

#### **TextView属性**

![](E:\Desktop\v2-1bdbe2eca06e14042251f6d00ee0a98a_hd.png)





TextView标签中“android:”后面的单词表示属性名，“=” 后面用引号包裹的部分表示属性值，通过这种“键 - 值”对的关系设定控件的一个个属性。这里为TextView添加的属性有：

Ø id属性：这个属性为控件指定了唯一的id号，通过这个id就可以在项目里的任何地方找到这个控件（可以认为是控件名），一般来讲，这个属性是必须的，格式比较固定“@+id/用户自定义名”。注意，设置这个属性值时要保证其唯一性。

Ø layout_width和layout_height属性：宽高属性，定义一个控件的大小，在Android studio中，每创建一个控件，这两个属性是会自动生成的，这也表明了它们是定义一个控件所必须的。常用的值有两个：match_parent（占满一行）、wrap_content（包裹内容），当然用户也可以自定义其大小，考虑到Android设备分辨率的多样性，一般采用dp作为单位。

Ø drawableRight属性：这个属性可以在TextView中插入图片，后面的Right后缀表明插入的位置（右边），当然要在左边插入要怎么做，相信读者也应该明白了。引号中是属性对应的值，前面的“@android：”表示这个图片是android系统内置的图片，若要引用项目drawable文件夹下的图片直接引用“@drawable”即可。

Ø gravity属性：这个属性一般用于控制控件内部内容在控件中的什么位置显示，在Android studio中输入快捷键：ctrl+alt+space，即可弹出gravity的所有属性值，如图4.1所示。



![img](https://pic3.zhimg.com/80/v2-fe042aea71bbb90a173d51267fda6be6_hd.png)



图4.1 gravity属性弹出窗

Ø singLine属性：中文译为单行模式，主要有两个值true和false。true表示单行模式、false表示多行模式，不设置这个属性时默认为false，即多行模式。

Ø text属性：这是TextView的核心属性，也就是TextView的显示内容。

Ø textColor属性：设置字体的颜色，其值是十六位的数字，也可以使用color文件中保存的颜色值。

Ø textSize属性：这个属性可以设置显示文本的字体大小，考虑到Android设备屏幕分辨率的多样性，一般采用sp作为单位。

Ø textStyle属性：这个属性用于设置字体的样式，android提供了三个值供开发者选用：bold（加粗）、italic（斜体）、normal（正常），其中normal为默认值。

#### **全屏显示设置**

**新建style**

打开styles.xml

![](E:\Desktop\TIM截图20200220185937.jpg)

```
<resources>

    <!-- Base application theme. -->
    <style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar">
        <!-- Customize your theme here. -->
        <item name="colorPrimary">@color/colorPrimary</item>
        <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
        <item name="colorAccent">@color/colorAccent</item>
    </style>
    <style name="AppTheme.FullScreen">
        <!-- Customize your theme here. -->
        <item name="windowActionBar">false</item>
        <item name="windowNoTitle">true</item>
        <item name="android:windowFullscreen">true</item>
    </style>


</resources>
```

**使用style**

![](E:\Desktop\TIM截图20200220190813.jpg)

### 2.3 对事件的监听

在LoginActivity中编辑

```
package com.test01;

import android.content.Intent;
import android.net.Uri;
import android.support.annotation.IdRes;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;

public class LoginActivity extends AppCompatActivity {
  //全局变量声明
    EditText username,pwd;  
    Button login,exit;
    TextView register,us;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_login_activtiy);
//获取事件源
        username = (EditText) findViewById(R.id.editText);
        pwd = (EditText) findViewById(R.id.editText2);
        login = (Button)findViewById(R.id.button);
        exit = (Button)findViewById(R.id.button2);
        register = (TextView)findViewById(R.id.textView4);
        us = (TextView)findViewById(R.id.textView5);

//使用匿名内部类实现监听
        login.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Toast.makeText(LoginActivity.this,"你为什么要点我？！", Toast.LENGTH_SHORT).show();
            }
        });

        register.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Intent intent = new Intent();
                intent.setClass(LoginActivity.this,RegisterActivity.class);
                startActivity(intent);
            }
        });
        us.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Uri uri = Uri.parse("tel:13000000000");
                Intent intent = new Intent(Intent.ACTION_DIAL,uri);
                startActivity(intent);
            }
        });



    }


}

```

#### **监听三要素**

**1. 事件源（Event Source）**产生事件的来源，通常是各种组件，如按钮，窗口等

**2.事件（Event）**事件封装了界面组件上发生的特定事件的具体信息，如果监听器需要获取界面组件上所发生事件的相关信息，一般通过事件Event对象来传递

**3.事件监听器（Event Listener）**：负责监听事件源发生的事件，并对不同的事件做相应的处理

#### **事件监听器**

在android系统中常见的事件监听器有如下几种：
a）单击事件（View.OnClickListener):

    当用户触碰到某个组件或者方向键被按下时产生该事件，该事件的处理方法是onClick();

b）焦点事件（View.OnFocusChangeListener):

     组件得到或者失去焦点时产生该事件，事件处理方法是onFocusChange()。

c）按键事件（View.OnKeyListener）：

    用户按下或者释放设备上的某个按键时产生，事件处理方法是onKey();

d）触碰事件（View.OnTouchListener）：

设备具有触摸屏功能时，触碰屏幕产生该事件，事件处理方法是onTouch();

e）创建上下文菜单事件（View.OnCreateContextMenuListener）：

创建上下文菜单时产生该事件，事件处理方法是onCreateContextMenu().

#### **事件处理步骤**

a)创建事件监听器。

b)给要响应事件的组件注册事件监听器。

c)在事件处理方法中编写实现代码。

![](E:\Desktop\TIM截图20200220193648.jpg)



## Intent

https://www.jianshu.com/p/67d99a82509b

作者：翻译不了的声响
链接：https://www.jianshu.com/p/67d99a82509b
来源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处

**简介**

Android中提供了Intent机制来协助应用间的交互与通讯，Intent负责对应用中一次操作的动作、动作涉及数据、附加数据进行描述，Android则根据此Intent的描述，负责找到对应的组件，将 Intent传递给调用的组件，并完成组件的调用。Intent不仅可用于应用程序之间，也可用于应用程序内部的 **Activity / Service**之间的交互。因此，Intent在这里起着一个媒体中介的作用，专门提供组件互相调用的相关信息，实现调用者与被调用者之间的解耦。

### **1. Intent作用**

Intent是一个将要执行的动作的抽象的描述，一般来说是作为参数来使用，由 Intent来协助完成 Android各个组件之间的通讯。比如说调用`startActivity()`来启动一个Activity，或者由`broadcaseIntent()`来传递给所有感兴趣的`BroadcaseReceiver`，再或者由`startService() / bindservice()`来启动一个后台的 service。所以可以看出来，Intent 主要是用来启动其他的 activity 或者 service，所以可以将 intent 理解成 activity 之间的粘合剂。

Intent作用的表现形式为：

- **启动Activity**
   通过`Context.startActvity() / Activity.startActivityForResult()`启动一个Activity；
- **启动Service**
   通过`Context.startService()`启动一个服务，或者通过`Context.bindService()`和后台服务交互；
- **发送Broadcast**
   通过广播方法`Context.sendBroadcasts() / Context.sendOrderedBroadcast() / Context.sendStickyBroadcast()`发给`Broadcast Receivers`

### **2. Intent种类**

- **显式Intent**
   显式，即直接指定需要打开的activity对应的类。

1）构造方法传入Component，最常用的方式：



```java
Intent intent = new Intent(this, SecondActivity.class);  
startActivity(intent);  
```

2）setComponent方法



```java
Intent intent = new Intent();    
intent.setClass(this, SecondActivity.class);  
//或者intent.setClassName(this, "com.example.app.SecondActivity");  
//或者intent.setClassName(this.getPackageName(),"com.example.app.SecondActivity");            
startActivity(intent);  
```

3）setClass / setClassName方法



```java
Intent intent = new Intent();    
intent.setClass(this, SecondActivity.class);  
//或者intent.setClassName(this, "com.example.app.SecondActivity");  
//或者intent.setClassName(this.getPackageName(),"com.example.app.SecondActivity");            
startActivity(intent);  
```

显式Intent通过Component可以直接设置需要调用的Activity类，可以唯一确定一个Activity，意图特别明确，所以是显式的。设置这个类的方式可以是Class对象（如`SecondActivity.class`），也可以是包名加类名的字符串（如`"com.example.app.SecondActivity"`）。

- **隐式Intent**
   隐式，不明确指定启动哪个Activity，而是设置Action、Data、Category，让系统来筛选出合适的Activity。筛选是根据所有的``来筛选。

### **3属性**

Intent对象大致包括7大属性：**Action（动作）**、**Data（数据）**、**Category（类别）**、**Type（数据类型）**、**Component（组件）**、**Extra（扩展信息）**、**Flag（标志位）**。其中最常用的是Action属性和Data属性。

### **4用法**

- 调用拨号程序

```dart
// 调用拨打电话，给10010拨打电话
Uri uri = Uri.parse("tel:10010");
Intent intent = new Intent(Intent.ACTION_DIAL, uri);
startActivity(intent);
```

```dart
// 直接拨打电话，需要加上权限 <uses-permission id="android.permission.CALL_PHONE" /> 
Uri callUri = Uri.parse("tel:10010"); 
Intent intent = new Intent(Intent.ACTION_CALL, callUri); 
```

- 发送短信或彩信

```dart
 // 给10010发送内容为“Hello”的短信
Uri uri = Uri.parse("smsto:10010");
Intent intent = new Intent(Intent.ACTION_SENDTO, uri);
intent.putExtra("sms_body", "Hello");
startActivity(intent);
```

```dart
// 发送彩信（相当于发送带附件的短信）
Intent intent = new Intent(Intent.ACTION_SEND);
intent.putExtra("sms_body", "Hello");
Uri uri = Uri.parse("content://media/external/images/media/23");
intent.putExtra(Intent.EXTRA_STREAM, uri);
intent.setType("image/png");
startActivity(intent);
```

- 通过浏览器打开网页

```dart
// 打开百度主页
Uri uri = Uri.parse("https://www.baidu.com");
Intent intent = new Intent(Intent.ACTION_VIEW, uri);
startActivity(intent);
```

- 发送电子邮件

```dart
// 给someone@domain.com发邮件
Uri uri = Uri.parse("mailto:someone@domain.com");
Intent intent = new Intent(Intent.ACTION_SENDTO, uri);
startActivity(intent);
```

```cpp
// 给someone@domain.com发邮件发送内容为“Hello”的邮件
Intent intent = new Intent(Intent.ACTION_SEND);
intent.putExtra(Intent.EXTRA_EMAIL, "someone@domain.com");
intent.putExtra(Intent.EXTRA_SUBJECT, "Subject");
intent.putExtra(Intent.EXTRA_TEXT, "Hello");
intent.setType("text/plain");
startActivity(intent);
```

```dart
// 给多人发邮件
Intent intent=new Intent(Intent.ACTION_SEND);
String[] tos = {"1@abc.com", "2@abc.com"}; // 收件人
String[] ccs = {"3@abc.com", "4@abc.com"}; // 抄送
String[] bccs = {"5@abc.com", "6@abc.com"}; // 密送
intent.putExtra(Intent.EXTRA_EMAIL, tos);
intent.putExtra(Intent.EXTRA_CC, ccs);
intent.putExtra(Intent.EXTRA_BCC, bccs);
intent.putExtra(Intent.EXTRA_SUBJECT, "Subject");
intent.putExtra(Intent.EXTRA_TEXT, "Hello");
intent.setType("message/rfc822");
startActivity(intent);
```

- 显示地图与路径规划

```dart
 // 打开Google地图中国北京位置（北纬39.9，东经116.3）
Uri uri = Uri.parse("geo:39.9,116.3");
Intent intent = new Intent(Intent.ACTION_VIEW, uri);
startActivity(intent);
```

```dart
// 路径规划：从北京某地（北纬39.9，东经116.3）到上海某地（北纬31.2，东经121.4）
Uri uri = Uri.parse("http://maps.google.com/maps?f=d&saddr=39.9 116.3&daddr=31.2 121.4");
Intent intent = new Intent(Intent.ACTION_VIEW, uri);
startActivity(intent);
```

- 播放多媒体

```dart
Intent intent = new Intent(Intent.ACTION_VIEW);
Uri uri = Uri.parse("file:///sdcard/foo.mp3");
intent.setDataAndType(uri, "audio/mp3");
startActivity(intent);

Uri uri = Uri.withAppendedPath(MediaStore.Audio.Media.INTERNAL_CONTENT_URI, "1");
Intent intent = new Intent(Intent.ACTION_VIEW, uri);
startActivity(intent);
```

- 选择图片

```cpp
Intent intent = new Intent(Intent.ACTION_GET_CONTENT);
intent.setType("image/*");
startActivityForResult(intent, 2);
```

- 拍照

```cpp
 // 打开拍照程序
Intent intent = new Intent(MediaStore.ACTION_IMAGE_CAPTURE);
startActivityForResult(intent, 1);
```

```csharp
 // 取出照片数据
Bundle extras = intent.getExtras();
Bitmap bitmap = (Bitmap) extras.get("data");
```

- 获取并剪切图片

```dart
// 获取并剪切图片
Intent intent = new Intent(Intent.ACTION_GET_CONTENT);
intent.setType("image/*");
intent.putExtra("crop", "true"); // 开启剪切
intent.putExtra("aspectX", 1); // 剪切的宽高比为1：2
intent.putExtra("aspectY", 2);
intent.putExtra("outputX", 20); // 保存图片的宽和高
intent.putExtra("outputY", 40);
intent.putExtra("output", Uri.fromFile(new File("/mnt/sdcard/temp"))); // 保存路径
intent.putExtra("outputFormat", "JPEG");// 返回格式
startActivityForResult(intent, 0);
```

```dart
// 剪切特定图片
Intent intent = new Intent("com.android.camera.action.CROP");
intent.setClassName("com.android.camera", "com.android.camera.CropImage");
intent.setData(Uri.fromFile(new File("/mnt/sdcard/temp")));
intent.putExtra("outputX", 1); // 剪切的宽高比为1：2
intent.putExtra("outputY", 2);
intent.putExtra("aspectX", 20); // 保存图片的宽和高
intent.putExtra("aspectY", 40);
intent.putExtra("scale", true);
intent.putExtra("noFaceDetection", true);
intent.putExtra("output", Uri.parse("file:///mnt/sdcard/temp"));
startActivityForResult(intent, 0);
```

- 打开手机应用市场

```dart
// 打开手机应用市场，直接进入该程序的详细页面
Uri uri = Uri.parse("market://details?id=" + packageName);
Intent intent = new Intent(Intent.ACTION_VIEW, uri);
startActivity(intent);
```

- 安装程序

```dart
String fileName = Environment.getExternalStorageDirectory() + "/myApp.apk";   
Intent intent = new Intent(Intent.ACTION_VIEW);   
intent.setDataAndType(Uri.fromFile(new File(fileName)),
"application/vnd.android.package-archive");   
startActivity(intent);  
```

- 卸载程序

```dart
Uri uri = Uri.parse("package:" + packageName);   
Intent intent = new Intent(Intent.ACTION_DELETE, uri);
startActivity(intent);
```

- 进入设置界面

```cpp
// 进入系统设置界面
Intent intent = new Intent(android.provider.Settings.ACTION_SETTINGS);
startActivity(intent);
```

## Toast

Toast是Android中用来显示显示信息的一种机制，和Dialog不一样的是，Toast是没有焦点的，而且Toast显示的时间有限，过一定的时间就会自动消失

## 3作业

2020.2.20

任务名称：简单的登录页面

难度：☆

评价：很简单，简单的令人发指

1.Login界面点击登录，如果用户名和密码是admin/123,提示登录成功，并跳转到MainActivity

2.若用户名不是admin，提示用户名不存在

3.若用户名不是admin，密码不是123，提示密码错误

```
login.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick(View v) {
                String username1 = username.getText().toString();//从输入框获得数据
                String password1 = pwd.getText().toString();
                if(username1.equals("admin")){
                    if(password1.equals("123")){
                        Toast.makeText(LoginActivity.this,"登录成功", Toast.LENGTH_SHORT).show();
                        Intent intent = new Intent();
                        intent.setClass(LoginActivity.this,MainActivity.class);//第一个是当前Activity，第二个是要跳转的Activity
                        startActivity(intent);
                        LoginActivity.this.finish();
                    }else{
                        Toast.makeText(LoginActivity.this,"密码错误", Toast.LENGTH_SHORT).show();
                    }

                }else{
                    Toast.makeText(LoginActivity.this,"用户名错误", Toast.LENGTH_SHORT).show();
                }

            }
        });
```

