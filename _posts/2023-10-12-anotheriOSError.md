---
layout: post
title: iOS development debuging error record - 2
date: 2023-10-12 22:10:10
description: Here is a iOS development debuging error record.
tags: iOS Error
categories: posts
giscus_comments: true
related_posts: true
---


你的 `scrollView` 可以轻微地上下滚动，这通常是由于两个原因：

1. **Content Insets**: 当你将 `scrollView` 嵌入在 `UINavigationController` 中，系统可能会自动为 `scrollView` 调整内容的插入（content insets），这样顶部的内容就不会被导航栏遮挡。这些 insets 可能会导致额外的上下滚动空间。

2. **Content Size**: `scrollView` 的 `contentSize` 如果稍微大于其本身的尺寸，它就会允许滚动。确保内容的高度与 `scrollView` 的高度完全匹配。

### 解决方法：

1. **禁用自动调整滚动视图插入**:
   你可以设置 `automaticallyAdjustsScrollViewInsets` 属性为 `false` 来禁用这种行为（在 iOS 11 之前使用）。在 iOS 11 及更高版本中，你应该使用 `contentInsetAdjustmentBehavior`。

```swift
override func viewDidLoad() {
    super.viewDidLoad()

    // For iOS 11 and later
    if #available(iOS 11.0, *) {
        scrollView.contentInsetAdjustmentBehavior = .never
    } else {
        // For iOS versions prior to 11
        automaticallyAdjustsScrollViewInsets = false
    }
    
    // ... Rest of your code
}
```

2. **固定 `scrollView` 的 `contentSize`**:
   在 `setupScrollView()` 方法的末尾，确保设置 `contentSize` 的高度与 `scrollView` 的高度相同。

```swift
scrollView.contentSize = CGSize(width: view.bounds.width * CGFloat(pages.count), height: view.bounds.height)
```

这样应该能确保 `scrollView` 不再上下滚动。