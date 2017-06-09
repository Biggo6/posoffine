
#Installation in Android Studio

Lets say you have kept aar file in libs folder. ( assume file name is ```izweboffline.aar``` )

then in app ```build.gradle``` specify following and click sync project with Gradle files.

```

allprojects {
   repositories {
      jcenter()
      flatDir {
        dirs 'libs'
      }
   }
}

dependencies {
    compile(name:'izweboffline', ext:'aar')
}

```

If everything goes well you will see library entry is made in build -> exploded-aar

Also note that if you are importing a .aar file from another project that has dependencies you'll need to include these in your build.gradle, too




