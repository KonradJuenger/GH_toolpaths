# Toolpaths

## -- STILL IN DEVELOPMENT --

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

1. install it via packagemanager: [install](rhino://package/search?name=toolpaths) or manually by running `_packagemanager` and then search for **Toolpaths**

   - check **include prerelease**
   - currently package manager on **Rhino for Mac** is broken, update to the current Release candiate > **Rhino 8 SR25 Release Candidate 2** 
1. restart Rhino and enter a license key or add a license key to your rhino account. Currently Beta testers get a key via email, after the beta check juengerkuehn.com/toolpaths for futher information. See [Licensing ](Docs/CORE/licensing.md)for details on the different licensing modes available.

#### overview ui 

|                                                                                     |                                                                                                      |
| ----------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| <img src="Images/Rhino_c4XbruyvUU.avif" alt="" style="max-width:100%;height:auto;"> | right click components to reveal parameters.                                                         |
| <img src="Images/Rhino_1zHBruW1qc.avif" alt="" style="max-width:100%;height:auto;"> | Toolpaths objects are geometry. you can transform them with the standart grasshopper components. (move, array, transform ...) |
| <img src="Images/Rhino_6G4t7lFxec.avif" alt="" style="max-width:100%;height:auto;"> | use **Toolpaths Generators** to create vasemode prints or infill                                     |
| <img src="Images/Rhino_IU8lO9lQS6.avif" alt="" style="max-width:100%;height:auto;"> | use **Toolpaths Modulators** to varie different parameters per segment like speed, flow, displacement |
| <img src="Images/Rhino_e2WsY8M4wt.avif" alt="" style="max-width:100%;height:auto;"> | combine Modulators with **Masks** to restrict the effect to specific regions or along a gradient     |
| <img src="Images/Rhino_urHorfmCqV.avif" alt="" style="max-width:100%;height:auto;"> | **Toolpath Operations** allows to group individual toolpath into one element. right click it to set parameters for the whole operatio |

#### Changelog

###### 0.1.5-alpha6

- option to disable licensing , plugin will not try to load automatically until licensing is enabled
- naming conflict resolved between Rhino host plugin and Grasshopper 

###### 0.1.4-alpha5

- licensing popup at first install