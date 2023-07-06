In order to create a root ViewController programmatically without using main.storyboard, you have to go to SceneDelegate.swift file

```
    var window: UIWindow?

func scene(_ scene: UIScene, willConnectTo session: UISceneSession, options connectionOptions: UIScene.ConnectionOptions) {
    // Use this method to optionally configure and attach the UIWindow `window` to the provided UIWindowScene `scene`.
    // If using a storyboard, the `window` property will automatically be initialized and attached to the scene.
    // This delegate does not imply the connecting scene or session are new (see `application:configurationForConnectingSceneSession` instead).
    guard let windowScene = (scene as? UIWindowScene) else { return }
    
    let vc = MSATabbarController() // This is the rootViewController
    let window = UIWindow(windowScene: windowScene)
    
    window.rootViewController = vc
    window.makeKeyAndVisible()
    
    self.window = window
}
```