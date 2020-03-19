# COVID-19 CORONAVIRUS OUTBREAK [![](https://jitpack.io/v/fsfaysalcse/CoronaOutbreakLib.svg)](https://jitpack.io/#fsfaysalcse/CoronaOutbreakLib)

Using this library you will find the following information about coronavirus-

- Coronavirus Cases
- Deaths
- Recovered

## Installation

To get a Git project into your build:

Step 1. Add the JitPack repository to your build file

```bash
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
```
Step 2. Add the dependency

```bash
dependencies {
	        implementation 'com.github.fsfaysalcse:CoronaOutbreakLib:0.1.0'
	}
```

## Usage

```java
Corona.setTotalOutbreakListener(MainActivity.this,new TotalOutbreakListener() {
                @Override
                   public void success(Response response) {
                    Log.d(TAG, "success: "+response.getMessage());
                     if (response.isSuccess()){
                                   Log.d(TAG, "Coronavirus Cases : "+response.getOutbreak().getTotalCases()+"\n"+
                                                   "Deaths : "+response.getOutbreak().getTotalDeaths()+"\n"+
                                                   "Recovered : "+response.getOutbreak().getTotalRecovered()
                                   );
                               }
                               dialog.dismiss();
                           }

                 @Override
                   public void failed(String errorMessage) {
                     Log.d(TAG, "failed: "+errorMessage);
                     dialog.dismiss();
                   }
        });
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update the tests as appropriate.
