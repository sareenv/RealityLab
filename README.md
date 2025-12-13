# HelloAR - Interactive AR Learning Experience 🚀

An immersive **Augmented Reality (AR)** educational application built with **SwiftUI** and **RealityKit/ARKit** that brings space exploration and scientific history to life through interactive 3D models and image recognition.

## 📱 Overview

HelloAR is an iOS application designed to make learning engaging through AR technology. The app features two main interactive experiences:

1. **3D Model Viewer**: Place and interact with space-related 3D models (Lunar Rover, Cosmonaut Suit, etc.) in your real-world environment
2. **Scientist Recognition Cards**: Use image tracking to recognize famous scientist cards and display their biographical information in AR

## ✨ Key Features

### 🌌 Interactive 3D Models
- **Lunar Rover**: Explore the vehicle used on Moon missions
- **Cosmonaut Suit**: View detailed space suit models used for EVAs
- **The HAB Module**: Examine the pressurized cargo carrier used in space missions
- **Volcano Model**: Learn about geological formations with interactive 3D visualization

### 🔬 AR Image Recognition
- Recognizes printed cards featuring famous scientists:
  - Marie Curie (Physics)
  - Albert Einstein (Physics)
  - Isaac Newton (Mathematics)
  - Charles Darwin (Biology)
  - Galileo Galilei (Astronomy)
  - Ada Lovelace (Mathematics)
  - Mary Anning (Palaeontology)
  - Louis Pasteur (Chemistry)
  - Nikola Tesla (Engineering)

### 🎯 Core Functionality
- **Plane Detection**: Automatically detects horizontal surfaces for model placement
- **Tap to Place**: Simple tap gesture to position 3D models in AR space
- **Image Tracking**: Real-time recognition of reference images with biographical overlays
- **Search Capability**: Quickly find specific models through the search interface
- **Async Image Loading**: Smooth loading of preview images with progress indicators

## 🏗️ Architecture

### Technology Stack
- **SwiftUI**: Modern declarative UI framework
- **RealityKit**: High-performance 3D rendering and AR experiences
- **ARKit**: Apple's augmented reality framework
- **SceneKit**: 3D graphics rendering (for scientist card view)
- **Combine**: Reactive programming for state management

### Project Structure
```
HelloAR/
├── App/
│   ├── AppDelegate.swift              # App lifecycle and window management
│   └── ContentView.swift              # Main navigation and model listing
│
├── Views/
│   ├── ARViewContainer.swift          # RealityKit AR view wrapper
│   └── DetailView.swift               # Model details and AR launcher
│
├── UIControllers/
│   └── ScientistController.swift     # ARKit image tracking controller
│
├── Coordinator/
│   └── Coordinator.swift              # AR gesture handling and model placement
│
├── Models/
│   ├── ObjectModel.swift              # 3D object data model
│   └── Scientist.swift                # Scientist biographical data model
│
├── Resources/
│   ├── scientists.json                # Scientist database
│   ├── AREntites/                     # .reality 3D model files
│   │   ├── CosmonautSuit.reality
│   │   ├── hab_en.reality
│   │   └── LunarRover.reality
│   ├── VOLCANO.usdz                   # Static USDZ model
│   └── Assets.xcassets/               # Images and AR reference images
│
└── Experience.rcproject/              # Reality Composer project
```

## 🚀 Getting Started

### Prerequisites
- **Xcode 13.0+**
- **iOS 14.0+** target device
- **ARKit-compatible device** (iPhone 6s or newer, iPad Pro, or later)
- Physical space (1-2 meters) for AR model placement

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/sareenv/ARL-SWIFTUI-Project.git
   cd ARL-SWIFTUI-Project
   ```

2. **Open the project**
   ```bash
   open HelloAR.xcodeproj
   ```

3. **Configure code signing**
   - Select the HelloAR target
   - Choose your development team in the "Signing & Capabilities" tab

4. **Build and Run**
   - Select a physical iOS device (AR requires a real device)
   - Press `Cmd + R` to build and run

### For Scientist Recognition Feature
To test the scientist recognition feature, you'll need physical cards with images of the scientists. The app recognizes images from the `Assets.xcassets/scientists.arresourcegroup/` directory.

## 💡 Usage Guide

### Viewing 3D Models
1. Launch the app and browse the model list
2. Tap on any model card to view details
3. Press **"Experience the Reality"** button
4. Point your device at a flat surface (table, floor)
5. Tap the screen to place the model
6. Move around to view from different angles

### Using Scientist Recognition
1. Select **"Scientist Recognizer"** from the card models section
2. Point your camera at a scientist reference card
3. The app will recognize the image and display:
   - Scientist's name
   - Life dates
   - Field of expertise
   - Biographical information

## 🎨 Features in Detail

### AR Model Placement
- Uses **ARKit plane detection** to find horizontal surfaces
- **Raycast technology** for accurate 3D positioning
- **Single-tap gesture** for intuitive model placement
- Automatically removes previous models when placing new ones

### Image Recognition System
- Leverages **ARImageTrackingConfiguration**
- Real-time tracking of multiple reference images
- Dynamic **3D text rendering** using SceneKit
- Custom text positioning and formatting for optimal readability

### User Interface
- **Searchable list** with categorized sections:
  - Space Interactive Models
  - Cards Interactive Models  
  - Static Learning Models
- **Async image loading** with placeholders
- **Navigation-based flow** for seamless user experience
- **Sheet presentation** for AR views

## 🔧 Technical Highlights

### RealityKit Integration
```swift
// Model loading and AR placement
let modelEntity = try? ModelEntity.load(named: modelName)
let anchorEntity = AnchorEntity(raycastResult: result)
anchorEntity.addChild(modelEntity)
```

### ARKit Image Tracking
```swift
// Configure image tracking
let configuration = ARImageTrackingConfiguration()
configuration.trackingImages = trackingImages
sceneView.session.run(configuration)
```

### SwiftUI + UIKit Bridge
Uses `UIViewRepresentable` and `UIViewControllerRepresentable` protocols to seamlessly integrate ARKit/SceneKit views into SwiftUI.

## 📝 Code Quality Improvements

This project has been updated with:
- ✅ Comprehensive inline documentation
- ✅ Improved code organization and file structure
- ✅ Better separation of concerns
- ✅ Enhanced readability and maintainability
- ✅ Clear architectural patterns

## 🐛 Known Limitations

- AR features require ARKit-compatible devices
- Camera permissions must be granted
- Adequate lighting is needed for optimal AR tracking
- Some 3D models may be large and require good device performance

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests
- Improve documentation

## 📄 License

This project was created as an educational demonstration. Please ensure you have the rights to use any 3D models or images in your own implementations.

## 👤 Author

**DataBunker (sareenv)**
- GitHub: [@sareenv](https://github.com/sareenv)
- Created: November 2022
- Updated: December 2025

## 🙏 Acknowledgments

- Apple's ARKit and RealityKit frameworks
- Wikipedia for scientist biographical data
- Reality Composer for 3D model management
- SwiftUI community for inspiration

## 📸 Screenshots

_Add screenshots of your app here showing:_
- Main navigation view with model list
- AR model placement in action
- Scientist card recognition feature
- Detail view with model information

---

**Built with ❤️ using Swift, SwiftUI, ARKit, and RealityKit**
