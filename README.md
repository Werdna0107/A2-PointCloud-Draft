# A2 PointCloud Draft

![A2 PointCloud Draft screenshot](./screen.PNG)

A lightweight single-file HTML tool for working with `.las` point clouds: alignment, slicing, tracing, measuring, PNG export and DXF export.

The main goal is simple: turn a point cloud slice into a clean CAD-ready reference without ReCap, Revit or heavy desktop software.

## Video demo

[Watch the video on YouTube](YOUTUBE_LINK_HERE)
## Features

* Open and view `.las` point clouds
* 3D navigation and top orthographic view
* Align point clouds by selected planes
* Create slices by `XY`, `XZ` or `YZ` planes
* Manual point picking on a slice
* Draw open or closed contours
* Measure segment lengths
* Orthogonalize traced contours
* Export traced lines to `DXF`
* Export clean `PNG` slice images
* PNG export with white or transparent background
* Scale bar for CAD image scaling
* Crosshair and magnifier for accurate manual tracing

## Supported format

Currently supported:

```text
.las — uncompressed LAS point clouds
```

Not supported yet:

```text
.laz
.ply
.pcd
.xyz
.txt
```

If you have a `.laz` file, convert it to uncompressed `.las` first.

## Interface overview

### File

Open a `.las` point cloud file.

### Display

Controls for point cloud visualization:

* point size;
* opacity;
* perspective view;
* orthographic view;
* top view;
* crosshair;
* magnifier.

### Align

Align the point cloud using three picked points on a plane.

Available alignment modes:

```text
XY → Z = 0
XZ → Y = 0
YZ → X = 0
```

Typical workflow:

1. Select `XY`.
2. Click `Pick 3 pts`.
3. Pick three points on the floor.
4. The cloud is aligned horizontally.

After that, another alignment can be applied using a wall plane to rotate the plan into building axes.

### Slice

Create a point cloud slice by selected plane.

Example:

```text
Plane: XY
Start: 1.20
Width: 0.30
```

This shows a horizontal slice:

```text
Z = 1.20 ... 1.50 m
```

This is useful for creating floor-plan references from point clouds.

### Drawing

Manual tracing tools for the active slice:

* pick points;
* undo last point;
* close a contour;
* measure segments;
* orthogonalize contours;
* export traced lines to DXF.

Picked drawing points are placed on the current slice plane. This makes it possible to manually reconstruct corners even if the point cloud itself has rounded or noisy corner geometry.

### PNG export

Export a clean PNG image from the current view or slice.

PNG export can create:

* white background;
* transparent background;
* red point cloud rendering;
* scale bar below the image;
* image without UI panels or dark viewer background.

This is useful for inserting a point cloud slice into CAD as a reference image.

### DXF export

Export traced segments as a simple DXF file.

The DXF contains manually drawn linework from the current slice and can be used as a CAD base for further drafting.

## Typical workflow

1. Open a `.las` file.
2. Align the point cloud by the floor.
3. Align the plan by a wall or main building axis.
4. Switch to top orthographic view.
5. Create a slice at the required height.
6. Trace walls, columns or other contours.
7. Run `Ortho align`.
8. Export the result to `DXF` or `PNG`.

## Limitations

* This is not a replacement for Revit, AutoCAD or professional Scan-to-BIM software.
* The tool is intended for quick point cloud interpretation and CAD reference preparation.
* Large point clouds may be opened as preview.
* Full aligned LAS export from a browser can be limited by browser storage restrictions.
* For heavy point cloud processing, a desktop/native version is a better approach.

## Use cases

* Floor-plan tracing from point clouds
* Building survey workflows
* Quick CAD reference generation
* Manual wall and column tracing
* Point cloud slice export to PNG
* Simple DXF linework generation
* Checking geometry after laser scanning

## How to run

Download the HTML file and open it in a browser.

Recommended browsers:

```text
Google Chrome
Microsoft Edge
```

## Repository contents

```text
PointCloudViewer.html   Main single-file application
screenshot.png          Program screenshot
README.md               Project description
```

## Author

A2 Engineering / A2 Blog

Telegram: https://t.me/a2blog
