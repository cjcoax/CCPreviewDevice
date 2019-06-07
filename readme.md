# CCPreviewDevice
Simple enum to be used when previewing SwiftUI view in a specific device.
Usually you have to do something like this:

```swift
#if DEBUG
struct LandmarkList_Previews : PreviewProvider {
    static var previews: some View {
        
        ForEach(["iPhone 8", "iPhone XS Max"].identified(by: \.self)) {
            deviceName in
			SomeView()
            .previewDevice(PreviewDevice(rawValue: deviceName))
        }
    }
}
#endif
```
In otder specify devices, you need to use error prone string name. Instead of that you can do something like this:

```swift
#if DEBUG
struct LandmarkList_Previews : PreviewProvider {
    static var previews: some View {
        
        ForEach([CCPreviewDevice.iPhone8.rawValue, CCPreviewDevice.iPhoneXsMax.rawValue].identified(by: \.self)) {
            deviceName in
            LandmarkList()
            .previewDevice(PreviewDevice(rawValue: deviceName))
        }
    }
}
#endif
```
## Usage

Just drag &drop CCPreviewDevice.swift into your project and you're ready to go.

## License
[MIT License](http://opensource.org/licenses/mit-license.php).
