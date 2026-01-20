# Toolpaths

## -- IN DEVELOPMENT -- closed beta release--

Toolpaths is a Grasshopper plugin for generating and simulating G-code. It's goal is to enable new ways of 3D printing and CNC milling while giving novices and experts alike  full control of the machines movement.

### Toolpaths principles

- **Smart Geometry**

  A Toolpath groups a curve and its parameters into a single geometric object. This lets you vary settings like speed or extrusion per path or per segment. Because it stays a standard Grasshopper geometry, it can still be transformed by regular components.
- **Progressive complexity**

  Settings are optional and stay out of the way until you need them. A clear hierarchy lets you define values at three levels: Defaults (lowest), Toolpath, and Operation (highest). Set a global default once, override it on a few toolpaths, or apply changes to an entire operation without duplicating inputs.
- **Accurate simulation**

  FDM is simulated as real material accumulation in world space — overlapping paths are reflected in the result. CNC simulation models material removal with high resolution. Both focus on fidelity and performance to provide reliable previews before you generate G-code.

#### Features FDM

- advanced preview that simulates the extrusion process
- value modulators to adjust flow, speed and other parameters per vertex
- modulator masking to further control surface effects
- Klipper, Reprap (Duet), Octoprint remote Gcode upload
- Z-hop and safe-Z handling
- retractions
- Bed mesh compensation and TCP offsets
- Temperature control 
- Absolute/relative E support

#### Features CNC ( aviable for beta testers)

- LinuxCNC and Fusion 360 tool library support with tool/holder visualization
- High-performance stock removal simulation
- LinuxCNC-flavor G-code compiler

#### Installation
For installation and licensing instructions, please refer to the [Licensing Documentation](Docs/CORE/licensing.md).

#### Beta Testing
TOOLPATHS is currently in closed beta. We are beta testing with a small team of dedicated designers and fabricators. If you want to contribute, ask for a key at toolpaths@juengerkuehn.com.

#### overview ui 

|                                                                                     |                                                                                                      |
| ----------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| <img src="Images/Rhino_c4XbruyvUU.avif" alt="" style="max-width:100%;height:auto;"> | right click components to reveal parameters.                                                         |
| <img src="Images/Rhino_1zHBruW1qc.avif" alt="" style="max-width:100%;height:auto;"> | Toolpaths objects are geometry. you can transform them with the standart grasshopper components. (move, array, transform ...) |
| <img src="Images/Rhino_6G4t7lFxec.avif" alt="" style="max-width:100%;height:auto;"> | use **Toolpaths Generators** to create vasemode prints or infill                                     |
| <img src="Images/Rhino_IU8lO9lQS6.avif" alt="" style="max-width:100%;height:auto;"> | use **Toolpaths Modulators** to varie different parameters per segment like speed, flow, displacement |
| <img src="Images/Rhino_e2WsY8M4wt.avif" alt="" style="max-width:100%;height:auto;"> | combine Modulators with **Masks** to restrict the effect to specific regions or along a gradient     |
| <img src="Images/Rhino_urHorfmCqV.avif" alt="" style="max-width:100%;height:auto;"> | **Toolpath Operations** allows to group individual toolpath into one element. right click it to set parameters for the whole operation |

#### Changelog

###### 0.2.1-beta1 to 0.2.6-beta6
- bug fixes
- faster slicing 
- image map example 
- variable infill example
- better degen defaults
- issue warnings if extusion is limited by nozzle size
- slicing component now accept mesh input (much faster)
- baked preview mesh is now split to match the sim time
- improved stability 
- deconstuct toolpath is now two components: deconstuct CNC and deconstruct FDM
- gha loading sequence fix on mac 

###### 0.2.0-beta0 
- mesh smoothing 
- refactored infill and wall generator
- modulators accepts linear curves
- demo files
- volume component to calculate the extrusion area based on width / height
- static mode more performant

###### 0.1.14-alpha15 
- fdm machine flattens toolpath input
- uv scaling input  for better textures flow along the extrusion
- bugfixes for preview

###### 0.1.13-alpha14 
- Infill Generator : robust handling for disjoint regions
- Infill Generator :  Start Point is now hidden ; right click to reveal
- smart selector for extrusion mode based on available inputs 
- bugfix: static mode now correctly ignores sampled heights
- closed paths are rendered more nicely

###### 0.1.12-alpha13
- toolpaths now has an icon

###### 0.1.11-alpha12
- interpolated vector field modulator
- simulation improvement:
    - heigthfield outlier filtering
    - extrusion smoothing 
    - dengenerate extrusion filtering
    - heightfield interpolation
- bugfix: sorting curves off by default
- icons for parameters
- deconstruct toolpath features hidden outputs for clarity
- color component features hidden inputs
- vms now should default to 2 for all modulators


###### 0.1.10-alpha11
- significant perf improvements in fdm program generation and simulation

###### 0.1.9-alpha10

- better icons
- significant perf improvements in fdm preview 

###### 0.1.8-alpha9

- icons
- curve divider respects closed/open state
- walls generator reworked to suppress duplicate control points
- introduction of simplify curve component

###### 0.1.7-alpha8

- planar slicer component: generates planar curves for "normal" printing
- bugfix in walls generator: holes are offest correctly

###### 0.1.6-alpha7

- async upload to printer
- refactor of vasemode layerheight 
- introduction of layerheight generator: creates a layerheights based on slope 
- better default values
- licensing popup when license is expired 

###### 0.1.5-alpha6

- option to disable licensing , plugin will not try to load automatically until licensing is enabled
- naming conflict resolved between Rhino host plugin and Grasshopper 

###### 0.1.4-alpha5

- licensing popup at first install