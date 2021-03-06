# BlenderProc

![](readme.png)

A procedural blender pipeline for image generation for deep learning.

Check out our arXiv paper (we are updating it from time to time): https://arxiv.org/abs/1911.01911

## General

In general, one run of the pipeline first loads or constructs a 3D scene, then sets some camera positions inside this scene and renders different types of images (RGB, depth, normals, etc.) for each of them.
The blender pipeline consists of different modules, where each of them performs one step in the described process.
The modules are selected, ordered and configured via a `.yaml` file.
 
To run the blender pipeline one just has to call the `run.py` script in the main directory together with the desired config file and any additional arguments.

```
python run.py config.yaml <additional arguments>
```

This runs all modules specified in the config file in a step-by-step fashion in the configured order.

## Functionality

The following modules are already implemented and ready to use:

* Loading: `.obj`, SUNCG, Replica scenes.
* Lighting: Set, sample lights or automatic lighting of SUNCG scenes.
* Cameras: Set, sample or load camera poses from file.
* Rendering: RGB, depth, normal and segmentation images.
* Merging: `.hdf5` containers.

For advanced usage which is not covered by these modules, own modules can easily be implemented.

## Examples

* [Basic scene](examples/basic/): Basic example 
* [Simple SUNCG scene](examples/suncg_basic/): Loads a SUNCG scene and camera positions from file before rendering color, normal, segmentation and depth images.
* [SUNCG scene with camera sampling](examples/suncg_with_cam_sampling/): Loads a SUNCG scene and automatically samples camera poses in every room before rendering color, normal, segmentation and depth images.
* [Replica dataset](examples/replica-dataset): Loads a replica room, samples camera poses and renders normal images.
* [COCO annotations](examples/coco_annotations): Writes to a `.json` file containing COCO annotations for the objects in the scene.

... And much more!

## First step

Now head on to the [examples](examples) and check the README there: get some basic understanding of the config files, start exploring our examples and get a gist about writing your own modules!

## Change log

See our [change log](change_log.md).
