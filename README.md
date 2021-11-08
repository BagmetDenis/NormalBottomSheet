# NormalBottomSheet
`NormalBottomSheet` makes it easy to add custom bottom sheets to your `SwiftUI` apps. 

## Features
- Dynamic height (works with `ScrollView` and **every** other view)
- Many options for **customization**
- Very **easy to use**
- Flick through feature

## Requirements 

- iOS 13
- Swift 5.3
- Xcode 12

## Installation

### Swift Package Manager

```
https://github.com/danielsaidi/BottomSheet.git
```

### CocoaPods

```
pod DSBottomSheet
```

## Usage
NormalBottomSheet is similar to the built-in Sheet:
```swift
struct ContentView: View {
    @State var showSheet: Bool = false
    
    public var defaultAnimation: Animation = .interpolatingSpring(stiffness: 300.0, damping: 30.0, initialVelocity: 10.0)
    
    var body: some View {
        ScrollView{
            Button {
                withAnimation(defaultAnimation){
                    showSheet.toggle()
                }
            } label: {
                Text("Open Or Close")
            }
        }
        .bottomSheet(isPresented: $showSheet, isHandler: false, isFixed: false) {
            VStack {
                Text("This is Test Bottom Sheet")
                    .foregroundColor(.black)
            }
            .background(Color.white)
        }
    }
}
```

## Demo app

This repo contains a basic demo app that demonstrates how to use the bottom sheet.

Just open the `Demo` project and run the app.
