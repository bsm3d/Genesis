# Genesis: Interactive Cellular Evolution Simulation

> **This code is free to use for educational purposes.**

## Introduction

Genesis is an interactive cellular evolution simulation that explores emergent behaviors and complex interactions within a self-organizing system. The project serves as a digital ecosystem where different cell families evolve, compete, cooperate, and form colonies based on simple rules that lead to complex behaviors.

This repository contains Genesis V.3, which serves as the foundation for the more advanced versions of the project. While this code isn't specifically optimized (later versions implement spatial partitioning via Quadtree and other optimizations), it provides a clear and well-commented foundation to understand the core concepts.


## Key Features

- **Interactive Cellular Simulation**: Watch and influence a dynamic ecosystem of evolving cells
- **Self-Organizing Colonies**: Cells form colonies with center and satellite roles
- **Emergent Behaviors**: Complex patterns emerge from simple rules
- **Multiple Cell Families**: Different cell types with unique behaviors and characteristics
- **Energy-Based Ecosystem**: Cells consume food, grow, reproduce, and die based on energy levels
- **User Interaction**: Click to heal cells or disturb areas of the simulation
- **Rich Visualization**: Connection lines, glow effects, and visual feedback
- **No Dependencies**: Pure HTML5/JavaScript (ES5 compatible) with no external libraries

## Concept & Design Philosophy

Genesis sits at the intersection of contemplative game and scientific simulation, drawing inspiration from concepts like:

- Turing patterns
- Cellular automata
- Emergent behaviors
- Mutation and evolution
- Games like SimLife

Unlike traditional cellular automata that follow rigid grid-based rules, Genesis implements a more organic approach with cells that move freely, interact based on proximity, and form dynamic social structures. The balance between competition and cooperation, predation and mutualism creates a dynamic ecosystem that evolves in surprising and sometimes unexpected ways.

## Cell Properties & Behaviors

### Core Cell Properties

Each cell in Genesis has several key properties:

- **Position (x, y)**: Location in the simulation space
- **Radius**: Physical size of the cell (related to energy level)
- **Color/Family**: Determines basic behavioral traits and appearance
- **Energy**: Vitality metric that affects size, reproduction, and survival
- **Speed (speedX, speedY)**: Velocity vector for movement
- **Colony Role**: 'none', 'center', or 'satellite' in colony formations

### Cell States

Cells can exist in various states:

- **Normal**: Standard functioning state
- **Poisoned**: Affected by poison food, losing energy faster
- **Dying (Obesity)**: Death animation when exceeding energy threshold  
- **Fragmenting**: Breaking apart from an attack
- **Poison Death**: Special death animation from poison

### Cell Families

The simulation features several distinct cell families, each with their own characteristics:

- **Blue (Pacific)**: Standard sociable cells, attracted to food sources
- **Red (Apex)**: Aggressive predatory cells, more inclined to cannibalism
- **Green (Herbivore)**: Cells immune to poison
- **Purple (Mystic)**: Balanced cells with synergistic capabilities
- **Turquoise (Harmonic)**: Highly adaptable cells with environmental resistance
- **Orange (Dynamic)**: High metabolism cells with rapid growth

Through collisions and interactions, cells can mutate into different families, allowing the ecosystem to evolve dynamically.

### Interactions

Cells interact in several key ways:

1. **Cannibalism**: Larger cells can consume smaller cells of the same family
2. **Fragmentation**: Small energetic cells can attack and fragment larger cells
3. **Mutation**: Cells of different families can combine to create new family types
4. **Colony Formation**: Large cells can become colony centers with satellite cells orbiting them
5. **Energy Transfer**: Cells exchange energy during collisions based on relative size
6. **Food Consumption**: Cells absorb food particles to gain energy
7. **Reproduction**: Cells can divide when bouncing off walls if they have sufficient energy

## Configuration Parameters

Genesis has numerous configurable parameters that adjust the behavior of the simulation:

```javascript
const config = {
  initialCellsPerFamily: 4,    // Initial number of cells per color family
  maxCells: 50,                // Maximum cell count
  overeatThreshold: 180,       // Energy threshold for overfeeding death
  attractionDistance: 100,     // Distance for attraction effect between cells
  fragmentationChance: 0.3,    // Chance of a fragmentation attack success
  cannibalismThreshold: 1.3,   // Size ratio needed for cannibalism
  collisionDampingFactor: 0.8, // Reduction in speed after a collision
  colonySpacing: 25,           // Minimum spacing between colony center and satellites
  connectionLineDistanceMin: 50, // Minimum distance for connection lines
  connectionLineDistanceMax: 150, // Maximum distance for connection lines
  cannibalismFlashDuration: 15,  // Duration of the cannibalism flash (frames)
  connectionLineWidth: 2,      // Thickness of the connection lines
  energieBoost: 20,            // Energy boost when clicking directly on a cell
  rayonImpact: 180,            // Radius of mouse impact in pixels
  poisonChance: 0.2,           // Chance that food spawns as poisoned
  poisonEnergyMultiplier: 2,   // Poisoned cells lose energy 2x faster
  poisonDeathGlowDuration: 30  // Duration of the death glow for poisoned cells
};
```

These parameters can be adjusted to create different ecosystem dynamics - from highly aggressive environments with frequent cannibalism to cooperative systems with more stable colonies.

## Food System

The food system provides energy to cells:

- **Regular Food**: White particles that provide energy to cells
- **Poisoned Food**: Green particles that poison cells, causing them to lose energy faster
- Food appears randomly throughout the simulation
- Cells must physically contact food to absorb it
- Food can be created when cells die or fragment

## Colony Formation

One of the most interesting emergent behaviors in Genesis is colony formation:

1. Larger cells can become colony centers if they have at least 2 nearby cells of the same family
2. Smaller cells become satellites that orbit around the center cell
3. Colonies provide strategic advantages through organization
4. Colony members maintain connection lines visualizing their social structure

## User Interaction

Users can interact with the simulation in several ways:

- **Click on cells**: Heal/boost their energy (+20 energy points)
- **Click on empty areas**: Create disturbance waves that affect nearby cells
- **Triple click**: Reset the simulation
- **Watch the stats panel**: Monitor population and event statistics in real-time

## Implementation Notes

This code is implemented in pure HTML5/JavaScript with no dependencies. It uses the Canvas API for rendering and basic event handling for user interaction.

Key implementation aspects:

- Main animation loop updating at browser refresh rate
- Object-oriented approach with Cell and Food classes
- Collision detection and response
- Visual effects (glows, flashes, connection lines)
- Canvas-based rendering with optimized drawing
- Statistics tracking and display

## Future Development

While this version serves as the foundation, future versions of Genesis implement:

- Quadtree spatial partitioning for efficient collision detection
- Additional cell families with unique behaviors
- More complex ecosystem dynamics
- Enhanced visualization and effects
- Audio-responsive elements
- Greater user interaction options

## Getting Started

To run Genesis:

1. Clone this repository
2. Open the HTML file in any modern browser
3. Watch the simulation unfold
4. Interact by clicking on cells or empty spaces

No build process, dependencies, or special setup required.

## License

This code is free to use for educational purposes.

---

Created by Benoit Saint-Moulin © 2025
www.bsm3d.com
www.linkedin.com/in/benoitsaintmoulin
