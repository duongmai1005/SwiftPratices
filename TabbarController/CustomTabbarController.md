In order to create custom TabbarController programmatically in Swift.

1. Create a TabbarController using create file with CocoaTouch Class.
2. In Tabbar Controller, we should create a setupTabs function. For example we have a Tabbar with 5 items in it.

```swift
private func setupTabs() {
    let homeVC = MSAHomeViewController()
    let billVC = MSABillsViewController()
    let inboxVC = MSAInboxViewController()
    let activityVC = MSAActivityViewController()
    let moreVC = MSAMoreViewController()
}
```

3. In order to navigate between Tabbar you should embedded these ViewController into a NavigationController.
```swift
private func setupTabs() {
    let homeVC = MSAHomeViewController()
    let billVC = MSABillsViewController()
    let inboxVC = MSAInboxViewController()
    let activityVC = MSAActivityViewController()
    let moreVC = MSAMoreViewController()
    
    let nav1 = UINavigationController(rootViewController: homeVC)
    let nav2 = UINavigationController(rootViewController: billVC)
    let nav3 = UINavigationController(rootViewController: inboxVC)
    let nav4 = UINavigationController(rootViewController: activityVC)
    let nav5 = UINavigationController(rootViewController: moreVC)
}
```

4. Setup Tabbar item title and image using this code below.
``` swift
    nav1.tabBarItem = UITabBarItem(title: "Home", image: UIImage(systemName: "house"), tag: 1)
    nav2.tabBarItem = UITabBarItem(title: "Bills", image: UIImage(systemName: "dollarsign.square"), tag: 1)
    nav3.tabBarItem = UITabBarItem(title: "Inbox", image: UIImage(systemName: "bell"), tag: 1)
    nav4.tabBarItem = UITabBarItem(title: "Activity", image: UIImage(systemName: "newspaper"), tag: 1)
    nav5.tabBarItem = UITabBarItem(title: "Others", image: UIImage(systemName: "line.3.horizontal"), tag: 1)
```

5. Apply all ViewController to TabbarController
``` swift
    setViewControllers([nav1, nav2, nav3, nav4, nav5], animated: true)
```