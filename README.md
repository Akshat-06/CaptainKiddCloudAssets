# Captain Kidd Candy Collect - Unity Assessment

This repository contains the completed Unity technical assessment for the Captain Kidd Candy Collect endless runner. 

## 🛠️ Technical Highlights

* **Addressables Integration:** Core game assets (Backgrounds, the Character, Obstacles, and Candies) are decoupled from the starting scene and loaded asynchronously via the Unity Addressables system.
* **Robust Loading Screen:** The asset loading process is wrapped in a complete `try-catch` workflow. It dynamically updates the UI to show the current download phase and safely handles network or URL failures by halting the game and displaying clear error messages.
* **New Input System:** To prevent known sub-asset data loss bugs when instantiating Addressable prefabs, player inputs are fetched and subscribed to dynamically at runtime (using `InputSystem.actions.FindAction`), making the character controller completely modular and crash-proof.
* **Spine Animation Integration:** The character logic cleanly bridges physics-based Rigidbody2D movement with Spine skeleton animation states.
* **Centralized Game State:** The core game loop (Menu, Playing, Profile, Game Over) is managed cleanly via event-driven state changes in the `GameHandler`.

## 🚀 How to Run the Project

1. Clone the repository and open it in **Unity 6000.3** *(Change this if you used a different specific version!)*.
2. Ensure your **Active Input Handling** is set to `Input System Package (New)` or `Both` in *Edit > Project Settings > Player*.
3. **Addressables Setup (Crucial):**
   * Open the **Addressables Groups** window (`Window > Asset Management > Addressables > Groups`).
   * Click **Build > New Build > Default Build Script** to generate the asset bundles.
   * Change the **Play Mode Script** dropdown in the Addressables window to **Use Existing Build** to accurately test the async loading process.
4. Open the main starting scene located in your `Assets/Scenes` folder.
5. Press Play!****
