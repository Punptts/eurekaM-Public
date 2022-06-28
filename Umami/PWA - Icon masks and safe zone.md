uplinks:: [[+ HOME]]
tags:: #type/tool⚙️  #status/boat🚤 #on/ui 

# PWA - Icon masks and safe zone
---
## Jot down...
### PWA - Icon masks and safe zone
Some platforms have their own preferred icon shape, but as web applications should work across multiple platforms, it is possible to indicate that an icon can have a user-agent-specified mask applied.

The safe zone is the area within a [maskable](https://w3c.github.io/manifest/#dfn-maskable) icon which is guaranteed to always be visible, regardless of user agent preferences.

It is defined as a circle with center point in the center of the icon and with a radius of 2/5 (40%) of the icon size, which means the smaller of the icon width and height, in case the icon is not square.

The safe zone is a centrally positioned circle, with radius 2/5 (40%) of the minimum of the icon's width and height. All pixels in this zone are guaranteed to be seen in all masks. Pixels outside the safe zone are not guaranteed to (but can) be visible depending on the applied mask.

---
## Reference
- https://w3c.github.io/manifest/#icon-masks
- https://stackoverflow.com/questions/56999363/what-is-the-safe-zone-in-android-image-asset-studio