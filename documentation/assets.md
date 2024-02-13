# Asset Reference

VivMe uses a level of abstraction between rendering an actual asset aqcuisition. This allows assets to be easily exchanged between built-in assets, web sourced assets, and other means ( possibly external plugins? ). The format of an asset reference table described as a json object is a string to string map

```json
{
  "assets": {
    "circle.sprite": "https://example.com/circle.png",
    "square.mask": "https://example.com/square-mask.png",
    "custom.mesh": "{\"vertices\":[[0,0,0],[0,0,1],[0,1,1]],\"triangles\":[[0,1,2]],\"uvs\":[[0,0],[0,1],[1,1]]}",
    "default.material": "https://example.com/default-material.json",
    "background.sprite": "data:image/jpeg;base64,/9j/2wCEAAgG..."
  }
}
```

**supported extension formats**

- sprite: jpg, png, gif (still), avif (still), webp (still)
  - planned support: apng, avif (animated), gif (animated), webp (animated), svg
- mask: **see "sprite"**
  - jpg is supported, though transparency is ideal for masking per colors
- material: see [VivMe Material Json](./rendering/materials.md)
- mesh: see [VivMe Mesh Json](./rendering/meshes.md)

Provided strings can be urls to files, url to json, json strings, or raw data in base64 format (with proper identifier, ex. "data:image/png...")
* planned support: relative file paths from zip files

The Asset Fetcher will user the asset reference configuration to fetch assets ahead of time. It will use the provided extensions to verify that the provided assets are valid.
