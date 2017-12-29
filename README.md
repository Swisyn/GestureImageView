# GestureImageView

This library has copied from [Jason Polites's gesture-imageview](https://github.com/jasonpolites/gesture-imageview "Jason Polite's GestureImageView") repository, fixed couple of bugs and merged with pull requests from other users.

> This is a simple Android View class which provides basic pinch and zoom capability for images.

> Can be used as a replacement for a standard ImageView when you want to include pinch and zoom.


#### Gradle

Add dependency in your build.gradle

```groovy
implementation 'com.cuneytayyildiz:gestureimageview:1.0.0'
```

#### Features:
1. Pinch zoom in place (i.e. zoom occurs from point of touch)
2. Panning with fling gesture
3. Double tap zoom
4. Configurable zoom boundaries (min/max)

#### Limitations:
1. Does not support Rotation
2. Does not support Pan and Zoom together
3. Not all methods of ImageView class are supported (will throw UnsupportedOperationException if strict is true)



Notes:
------
1. Setting gesture-image:strict to true will result in UnsupportedOperationException if an unsupported method is called. Default value: false
2. Setting gesture-image:recycle to true will automatically reycle bitmap images when the view is destroyed. Default value: false

#### Usage
Configured as View in layout.xml
```xml

	<LinearLayout 
	    xmlns:android="http://schemas.android.com/apk/res/android"
	    xmlns:gesture-image="http://schemas.polites.com/android"
	    android:layout_width="fill_parent"
	    android:layout_height="fill_parent">

	    <com.cuneytayyildiz.gestureimageview.GestureImageView
	      android:id="@+id/image"
	      android:layout_width="fill_parent"
	    	android:layout_height="wrap_content" 
	    	android:src="@drawable/image"
	    	gesture-image:min-scale="0.1"
	    	gesture-image:max-scale="10.0"
	    	gesture-image:strict="false"/>
	    	
	</LinearLayout>
```

Configured Programmatically
```java  	

	import com.cuneytayyildiz.gestureimageview.GestureImageView;
	
	import android.app.Activity;
	import android.os.Bundle;
	import android.view.ViewGroup;
	import android.widget.LinearLayout.LayoutParams;
	
	public class SampleActivity extends AppCompatActivity {
	    @Override
	    public void onCreate(Bundle savedInstanceState) {
	        super.onCreate(savedInstanceState);
	        setContentView(R.layout.main);
	        
	        LayoutParams params = new LayoutParams(LayoutParams.WRAP_CONTENT, LayoutParams.WRAP_CONTENT);
	        
	        GestureImageView view = new GestureImageView(this);
	        view.setImageResource(R.drawable.image);
	        view.setLayoutParams(params);
	        
	        ViewGroup layout = (ViewGroup) findViewById(R.id.layout);
	
	        layout.addView(view);
	    }
	}
	```
  
  #### All pull requests are accepted, let's make this library great again! :P
