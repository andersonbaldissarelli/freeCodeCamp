---
title: Flutter
localeTitle: Flutter
---

# Google Maps para Flutter

### Uso
Para usar o plugin, adicione ``` google_maps_flutter: ``` como dependência no seu arquivo **pubspec.yaml**.

### Começando
Obtenha uma API KEY [aqui](https://cloud.google.com/maps-platform/.)

### Android
Especifique sua chave de API no arquivo manifest ```android/app/src/main/AndroidManifest.xml``` :

```
<manifest ...
  <application ...
    <meta-data android:name="com.google.android.geo.API_KEY"
               android:value="YOUR KEY HERE"/>
```

### iOS
Especifique sua chave de API no delegate ```ios/Runner/AppDelegate.m``` :

```
#include "AppDelegate.h"
#include "GeneratedPluginRegistrant.h"
#import "GoogleMaps/GoogleMaps.h"

@implementation AppDelegate

- (BOOL)application:(UIApplication *)application
    didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
  [GMSServices provideAPIKey:@"YOUR KEY HERE"];
  [GeneratedPluginRegistrant registerWithRegistry:self];
  return [super application:application didFinishLaunchingWithOptions:launchOptions];
}
@end
```

Ou no seu código em Swift, especifique sua chave de API no delegado em ```ios/Runner/AppDelegate.swift``` :

```
import UIKit
import Flutter
import GoogleMaps

@UIApplicationMain
@objc class AppDelegate: FlutterAppDelegate {
  override func application(
    _ application: UIApplication,
    didFinishLaunchingWithOptions launchOptions: [UIApplicationLaunchOptionsKey: Any]?
  ) -> Bool {
    GMSServices.provideAPIKey("YOUR KEY HERE")
    GeneratedPluginRegistrant.register(with: self)
    return super.application(application, didFinishLaunchingWithOptions: launchOptions)
  }
}
```
### Ambos

Agora você pode adicionar um widget do ```GoogleMap``` à sua árvore de widgets.
A visualização do mapa pode ser controlada com o ```GoogleMapController``` que é passado para o retorno de chamada ```onMapCreated``` do 
```GoogleMap```.



