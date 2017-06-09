
## Installation in Android Studio

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



## Usage

In your activity    ```onCreate``` method, 

```

Offline.setBaseUrl("http://192.168.43.73/poss/public/api/");
customerController = CustomerController.with(MainActivity.this);
        
```

## API

- Sync with Remote use the following

```

ServerCalls.synRemote

```

-- Laravel Integration

```
Route::post('api/synRemote', function(){
        $all   = request()->all();
        $total = $all['total'];

        for($i=1; $i<=$total; $i++){
            
            $acc_no    = "account_" . $i;
            $amount_no = "amount_" . $i;
            $status_no = "status_" . $i;

            $acc       = $all[$acc_no];
            $amount    = $all[$amount_no];
            $status    = $all[$status_no];
           
           // save to db the customer

        }

        return "OK";
});
```
