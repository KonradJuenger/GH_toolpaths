# Toolpaths

## STILL IN DEVELOPMENT / NO CODE / NO PACKAGE

Toolpaths is a Grasshopper plugin for generating and simulating G-code. It's goal is to enable new ways of 3D printing and CNC milling while giving novices and experts alike  full control of the machines movement.



### Toolpaths principles

- Parameterized geometry
  A Toolpath groups a curve and its parameters into a single geometric object. This lets you vary settings like speed or extrusion per path or per segment. Because it stays a standard Grasshopper geometry, it can still be transformed by regular components.

- Progressive complexity
  Settings are optional and stay out of the way until you need them. A clear hierarchy lets you define values at three levels: Defaults (lowest), Toolpath, and Operation (highest). Set a global default once, override it on a few toolpaths, or apply changes to an entire operation without duplicating inputs.

- Accurate simulation
  FDM is simulated as real material accumulation in world space — overlapping paths are reflected in the result. CNC simulation models material removal with high resolution. Both focus on fidelity and performance to provide reliable previews before you generate G-code.

#### Features FDM

- Per-segment flow/speed via modulators
- Z-hop and safe-Z handling
- retractions
- Bed mesh compensation and TCP offsets
- Temperature control 
- Absolute/relative E support
- Klipper, Reprap (Duet), Octoprint remote Gcode upload

#### Features CNC ( aviable for beta testers)

- LinuxCNC and Fusion 360 tool library support with tool/holder visualization
- High-performance stock removal simulation
- LinuxCNC-flavor G-code compiler


#### Installation 

...  get it from yak 
...  get a key 
...  install the key

#### Getting started

[FDM](Docs/intrFDM_Overview.md)