# Rendering

VivMe will be using Three.js to render 2d sprites into a 3d environment. This is to allow for the features needed to make complex animations possible using mesh warping and custom shaders. The renderer will use a configuration object to render the images in the correct transforms, and will apply warping, and other custom behaviours through the use of plugins.

On top of the configuration file, VivMe will allow the use of variables as inputs to transform data, as well as inputs to plugins. As a whole, this should allow for the custom animations of characters and other models, with live inputs.

the basic configuration file will include: sprite, transform (position, rotation, scale), parent, children, plugins, mesh, material.

nested sprites will inherit the transform data from its parent sprite.

A transform may contain 1 sprite, 1 mask, or both. Multiple masks should be placed on seperate transforms.

```json
// sprite transform
{ 
    "name": "circle",
    "parent": "global",
    "transform": {
        "matrix": [
            0, 0, 0, 0,
            0, 0, 0, 0,
            0, 0, 0, 0,
            0, 0, 0, 0
        ] 
    },
    "sprite": {
        "enabled": "true",
        "material": "standard.material",
        "mesh": "12x12.mesh",
        "image": "circle.sprite",
        "plugins": [
            "shimmer.plugin"
        ],
        "masks": []
    }, 
    "mask": {
        "enabled": "false",
        "material": "transparent.material",
        "mesh": "custom.mesh",
        "image": "square.mask",
        "plugins": [
            "wavy.plugin"
        ],
        "masks": []
    }
}
```
```json
/// indexed mesh json object
{
    "vertices": [
        [ 0, 0, 0 ],
        [ 0, 0, 1 ],
        [ 0, 1, 1 ]
    ],
    "triangles": [
        [ 0, 1, 2 ]
    ],
    "uvs": [
        [ 0, 0 ], 
        [ 0, 1 ], 
        [ 1, 1 ]
    ]
}
```
**note**
* the name "global" is a reserved name,
* Mesh can be provided in the following formats
    * a string in the format "axb.mesh", where a square mesh will be generated  with a vertices wide, and b vertices tall.
    * an asset reference, following the correct format for an indexed mesh 
        * an asset reference can be pointed directly to json text
        * A mesh asset reference can be provided by a url, as long as that url matches the correct formatting and points to a .json file

In a model configuration file there will be an objects array, which will contain all objects as part of its configuration
