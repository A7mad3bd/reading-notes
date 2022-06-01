# Read39
# Android Location

- using Google play services locatoin APIs, apps can request the last known location of the user's device.
- `fused location provider` is one of the location APIs in GP services- it manages the underlying location tech and provides a simple API so that you can specify requirements at a high level such as accuracy or low power and optimizes the device's use of battery power.

## Create location services client

- in your activity's `onCreate()` method, create an instance of the Fused Location Provider Client

```
private FusedLocationProviderClient fusedLocationClient;

// ..

@Override
protected void onCreate(Bundle savedInstanceState) {
    // ...

    fusedLocationClient = LocationServices.getFusedLocationProviderClient(this);
}
```

## Get the last known location

- use the `getLastLocation()` method to retrieve the device's location.
- the precise location returned is determined by the permission setting you put in the app manifest.
- the following code snippet illustrates the request and handling of the response:

```
fusedLocationClient.getLastLocation()
        .addOnSuccessListener(this, new OnSuccessListener<Location>() {
            @Override
            public void onSuccess(Location location) {
                // Got last known location. In some rare situations this can be null.
                if (location != null) {
                    // Logic to handle location object
                }
            }
        });
```

- `getLastLocation()` returns a `Task` that you can use to get a `Location` object with the latitude and longitude coordinates of a geographic location.
- location object may be null in the following situation:
    - Location is turned off in the devices settings- disabling location also clears the cache.
    - device never recorded its location - device is new or has been restored to factory settings.
    - Google Play services on the device has restarted, and there is no active Fused Location Provider client that has requested location after the services restarted.

  ## Choose the best location estimate

- `FusedLocationProviderClient` provides several methods to retrieve device location information:
    - `getLastLocation()` - gets a location estimate more quickly and minimizes battery usage that can be attributed to your app but location might be out of date if no other clients have actively used location recently.
    - `getCurrentLocation()` - get a newer, more accurate location more consistently. Can cause active location computation to occur on the device.
- this is the recommended way to get a fresh location, whenever possible as its safe than alternatives like starting and managing location updates yourself using `requestLocationUpdates()`- this can consume lasrge amounts of power if location isn't available or if the request isn't stopped correctly after getting a new location.


### Resources

[Android Location](https://developer.android.com/training/location/retrieve-current)