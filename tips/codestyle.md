# Code Style Guide

## Java Code Style
For the backend Java projects, it is recommended to follow the slightly modified Google Code Style.
https://google.github.io/styleguide/javaguide.html

1. Follow the Google Style except the item 2 and 3.
2. Block indentation: 4 spaces (instead of 2 spaces)
3. Column limit: 120 characters (instead of 100 characters)

## Code Formatting & Import Organizing
If you have some problem with applying the code style manually, it is also recommended to use auto-formatting or import organizing using IDEs with either Eclipse or IntelliJ IDEA.

Using the Google Style with the latest version of Eclipse and IntelliJ IDEA will reformat the code slightly different from each other. Also the files include unnecessary style informations for other languages. Please do not directly import the Google Style files (https://github.com/google/styleguide) to your IDE, but use the following AutoGraviy style files.

If you use import organizing with Eclipse, please update the importorder file to generate the same style of imports as with IntelliJ Idea.  

### Eclipse (JEE Neon.2)
* Import code style: autogravity-style-eclipse.xml and autogravity-style-eclipse.importorder
* Format code using Shift+Command+F.
* Organize imports using Shift+Command+O.

### IntelliJ IDEA (2016.3)
* Import code style: autogravity-style-intellij.xml
* Format code using Option+Command+L.
* Use auto import options (imports on the fly).

### Noticeable Changes from the Google Style Files
* Indentation/Tab size: 4
* Maximum line width: 120
* Maximum line width for comments: 120
* Never join already wrapped lines
* Insert new line in empty block (Eclipse)
* Disable block comment formatting (Eclipse)
* Line comment at first column (Eclipse)
* Blank lines fixes (Eclipse)
* Import layout/order fixes (Eclipse)
* Line wrapping fixes (IntelliJ IDEA)
* Wrap always on class, method and field annotations (IntelliJ IDEA)

## Other Resources
* AOSP Java Code Style for Contributors: https://source.android.com/source/code-style