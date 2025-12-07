# AR Dinosaur Viewer  
### View a 3D T-Rex Model in the Browser and in Augmented Reality

This project is a simple Web-based 3D + AR experience using **Google's model-viewer library**.  
It allows you to:

- Rotate and zoom a 3D dinosaur model inside the webpage  
- Press a button to view the dinosaur in **Augmented Reality (AR)** on supported devices  
- Reset camera, toggle rotation, view instructions  
- Load your own .glb 3D models

This is a beginner-friendly AR project — no Unity, no ARKit/ARCore coding.  
Just HTML + JS + model-viewer.


## What This Project Does

This webpage:

1. Loads a **T-Rex .glb file** into a 3D viewer.  
2. Lets the user rotate, zoom, and interact with the 3D model.  
3. Detects if the user’s phone supports WebXR / ARCore / ARKit.  
4. If supported → allows launching AR via the **“View in AR”** button.  
5. Displays the dinosaur in real-world space using the device’s camera.  
6. Provides controls like:
   - Reset View  
   - Toggle Auto-Rotation  


## Technologies Used

### model-viewer (Google)  
This is a web component that makes 3D & AR extremely easy.  
It handles:

- 3D rendering  
- Lighting & shadows  
- Touch interactions  
- AR launching  
- ARCore / ARKit compatibility

### HTML + CSS  
Used for layout, design, and responsiveness.

### JavaScript  
Used to:

- Detect AR support  
- Activate AR  
- Control camera settings  
- Toggle rotation  
- Handle errors  


## How to Run This Project

### **Method 1: Open locally**
You can open `index.html` directly, but:

**AR will NOT work from a local file path.**  
AR needs a **web server**.


### **Method 2: Run using VS Code + Live Server (Recommended)**

1. Install the **Live Server** extension  
2. Right-click `index.html` → **Open with Live Server**  
3. On your phone, open the same local network IP shown by Live Server  
4. Tap **View in AR**

This allows full WebXR AR functionality.


### **Method 3: Upload Online**
Host the project on:

- GitHub Pages  
- Netlify  
- Vercel  
- Firebase Hosting  

Use **HTTPS** for AR support.


## AR Support Requirements

### **Android**
- Chrome  
- ARCore-compatible device  
- .glb loads in WebXR mode

### **iOS**
- Safari  
- iOS 12+  
- QuickLook support  
  (<model-viewer> auto-converts the model for AR)

If unsupported → the button shows **“AR Not Available”**.


## File Structure
project/<br>
│ index.html → Main webpage<br>
│ TRex.glb → 3D model (replace with your own)<br>
└── assets/ → (optional)<br>


## How model-viewer Works in This Project

Example:

```
html
<model-viewer
    src="./TRex.glb"
    auto-rotate
    camera-controls
    ar
    ar-modes="webxr scene-viewer quick-look"
></model-viewer>
```


## What model-viewer Gives You

- 3D rendering  
- Orbit controls  
- AR button  
- WebXR + QuickLook support  
- Shadows & lighting  


## JavaScript Controls Explained

### **Reset Camera**
```js
modelViewer.cameraOrbit = '0deg 75deg 2.5m';
```

### **Toggle Rotation**
Adds or removes the `auto-rotate` attribute.

### **Error Handling**
Alerts the user if the .glb file path is incorrect or if AR activation fails.


## Customizing the Model

### **Replace the .glb file**
```
TRex.glb → myModel.glb
```

### **Update the viewer code**
```html
src="./myModel.glb"
alt="My 3D Model"
```

### **You can load any 3D model type**
- Buildings  
- Characters  
- Cars  
- Your own 3D creations  


## Future Improvements

- Add animation controls  
- Add model selector  
- Add custom lighting  
- Add AR placement anchors  
- Add multiple models in one scene  


## Summary

This project is a simple introduction to Web-based AR:

- No Unity  
- No native apps  
- Runs directly in the browser  
- Works on most phones  
- Perfect for demos, product previews, and AR learning  
