[![Release](https://img.shields.io/github/tag/panzerfahrer/svg-android.svg?label=JitPack)](https://jitpack.io/#panzerfahrer/svg-android/svg-android-2.0.7)


Gradle
=====

```groovy
repositories {
        maven { url "https://jitpack.io" }
}
 
dependencies {
        compile 'com.github.panzerfahrer:svg-android:svg-android-2.0.7'
}
```

Usage
=====

Firstly, store your SVGs in `res/raw` or `assets`.

```java
// Load and parse a SVG
SVG svg = new SVGBuilder()
            .readFromResource(getResources(), R.raw.someSvgResource) // if svg in res/raw
            .readFromAsset(getAssets(), "somePicture.svg")           // if svg in assets
            // .setWhiteMode(true) // draw fills in white, doesn't draw strokes
            // .setColorSwap(0xFF008800, 0xFF33AAFF) // swap a single colour
            // .setColorFilter(filter) // run through a colour filter
            // .set[Stroke|Fill]ColorFilter(filter) // apply a colour filter to only the stroke or fill
            .build();

// Draw onto a canvas
canvas.drawPicture(svg.getPicture());

// Turn into a drawable
Drawable drawable = svg.createDrawable();
// drawable.draw(canvas);
// imageView.setImageDrawable(drawable);
```
