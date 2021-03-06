# Printama
Android library for bluetooth thermal printer.

![Struk Belanja](images/struk_belanja.jpeg)
![Print Text Image](images/print_text_image.jpeg)
![Print Image Full Width](images/print_image_full.jpeg)
![Rose Photo](images/rose.jpeg)
![Printed Rose](images/rose_print.jpeg)
![Layout View](images/layout.jpeg)
![Printed Layout View](images/print_layout.jpeg)

## Usage
Currently still in Alpha. Make sure to use java 8+ configuration.
Documentation is in progress. Just take a look at sample project as an
example.

But here for an insight:

**Show dialog to choose bonded device** bind your device initially from
the bluetooth config:
```java
Printama.showPrinterList(this, printerName -> {
    ...
});
```

**Prepare the text**
```java
String text = "-------------\n" +
                "This will be printed\n" +
                "Left aligned\n" + // or Center or Right
                "cool isn't it?\n" +
                "------------------\n";
```

**Print Text LEFT aligned**
```java
Printama.with(context).connect(printama -> {
    printama.printText(Printama.LEFT, text);
    printama.close();
});
```

**Print Text CENTER aligned**
```java
Printama.with(context).connect(printama -> {
    printama.printText(Printama.CENTER, text);
    printama.close();
});
```

**Print Text RIGHT aligned**
```java
Printama.with(context).connect(printama -> {
    printama.printText(Printama.RIGHT, text);
    printama.close();
});
```

**Print Bitmap / Image LEFT aligned**
```java
Bitmap bitmap = BitmapFactory.decodeResource(getResources(), R.mipmap.ic_launcher);
Printama.with(context).connect(printama -> {
    printama.printImage(Printama.LEFT, bitmap, 200);
    printama.close();
});
```

**Print Bitmap / Image CENTER aligned**
```java
Bitmap bitmap = BitmapFactory.decodeResource(getResources(), R.mipmap.ic_launcher);
Printama.with(context).connect(printama -> {
    printama.printImage(Printama.CENTER, bitmap, 200);
    printama.close();
});
```

**Print Bitmap / Image RIGHT aligned**
```java
Bitmap bitmap = BitmapFactory.decodeResource(getResources(), R.mipmap.ic_launcher);
Printama.with(context).connect(printama -> {
    printama.printImage(Printama.RIGHT, bitmap, 200);
    printama.close();
});
```

**Print Bitmap / Image FULL size**
```java
Bitmap bitmap = BitmapFactory.decodeResource(getResources(), R.mipmap.ic_launcher);
Printama.with(context).connect(printama -> {
    printama.printImage(bitmap, Printama.FULL_WIDTH);
    printama.close();
});
```

**Print Bitmap / Image ORIGINAL size**
```java
Bitmap bitmap = BitmapFactory.decodeResource(getResources(), R.mipmap.ic_launcher);
Printama.with(context).connect(printama -> {
    printama.printImage(bitmap); // original size, centered as default
    printama.close();
});
```

**Print Drawable Vector**
```java
Bitmap bitmap = Printama.getBitmapFromVector(this, R.drawable.ic_launcher_background);
Printama.with(this).connect(printama -> {
    printama.printImage(bitmap, Printama.ORIGINAL_WIDTH);
    printama.close();
});
```

**Print Layout View**
using print layout view, you can design your receipt on your layout xml or dsl, and pass the root view as parameter
```java
View view = findViewById(R.id.root_view);
Printama.with(this).connect(printama -> {
    printama.printFromView(view);
    printama.close();
});
```

## Feature
* Dialog to choose bonded bluetooth device list.
* Print Text with Custom Alignment.
* Print auto grayscale Bitmap with Custom width and Alignment.
* Print photo (grayscaled)
* Print your android screen or layout by passing the root view
* Print vector drawable
* Tested with 2 inch Bluetooth Thermal Printers.


## Contributing

You can simply :
* a pull request, or
* raise an issue ticket, or
* request additional feature by raise a ticket.


## Download

Minimum Android SDK Version 16

#### Gradle
**Step 1.** Add it in your root build.gradle at the end of repositories:
```gradle
allprojects {
  repositories {
    ...
    maven { url 'https://jitpack.io' }
  }
}
```

**Step 2.** Add the dependency
```gradle
dependencies {
  implementation 'com.github.anggastudio:Printama:0.9.1'
}
```
#### Other like Maven, SBT, Leiningen
**just visit the jitpack page**
[Printama Jitpack](https://jitpack.io/#anggastudio/Printama)

## License

[Apache License 2.0](LICENSE)


## Thanks To:

- [imrankst1221](https://github.com/imrankst1221/Thermal-Printer-in-Android)
- [MFori](https://github.com/MFori/Android-Bluetooth-Printer)
- WP

## Contributor:

- [utsmannn](https://github.com/utsmannn)
- you (maybe)
