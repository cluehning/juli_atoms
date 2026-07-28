# Atom - Mathematical and Computational Visualization of Hydrogenic
Orbitals

A real-time OpenGL visualization of hydrogenic atomic orbitals, probability density, and quantum flow.

This project was inspired by Kavan's atom simulation:

- **Kavan's Atom Project:** https://github.com/kavan010/Atoms

The goal of this project is not only to render atomic orbitals, but also to provide an interactive environment for exploring the mathematical structure of hydrogen wavefunctions through the quantum numbers \(n\), \(l\), and \(m\).

For the complete mathematical derivations, Schrödinger equation solutions, probability density sampling methods, and probability current discussion, see **Atom (1).pdf**.

---

# Project Structure

```text
tzhe/
│
├── src/
│   └── atom_realtime.cpp      # Main realtime renderer
│
├── bin/
│   └── atom_realtime.exe      # Built executable
│
├── docs/
│   └── Atom (1).pdf          # Mathematical documentation
│
├── data/
│   └── orbital datasets
│
└── README.md
```

---

# Running the Project

## Recommended (VS Code)

1. Open the project in VS Code.
2. Press **Ctrl + Shift + P**.
3. Select **Run Task**.
4. Choose:

```text
Run Atom (3D realtime)
```

The project will build and launch automatically.

---

## Manual Build Command

The VS Code task executes:

```powershell
set PATH=C:\msys64\ucrt64\bin;%PATH% && ^
g++.exe -g src\atom_realtime.cpp ^
-o bin\atom_realtime.exe ^
-IC:/msys64/ucrt64/include ^
-LC:/msys64/ucrt64/lib ^
-lglfw3 -lglew32 -lopengl32 -lgdi32 -lglu32 && ^
.\bin\atom_realtime.exe
```

### Build Environment

- MSYS2 UCRT64
- GLFW
- GLEW
- OpenGL

---

# Interactive Exploration

The main purpose of the project is experimentation and intuition building.

While the renderer is running, you can modify the hydrogen quantum numbers in real time and observe how the orbital changes.

## Controls

| Key | Action |
|------|---------|
| W | Increase `n` |
| S | Decrease `n` |
| E | Increase `l` |
| D | Decrease `l` |
| R | Increase `m` |
| F | Decrease `m` |

## Quantum Numbers

### Principal Quantum Number (`n`)

Controls the energy level and overall size of the orbital.

Increasing `n` generally:

- Produces larger orbitals
- Adds radial structure
- Introduces additional nodes

### Angular Momentum Quantum Number (`l`)

Controls orbital shape.

Changing `l` transforms the geometry of the orbital:

- `l = 0` → s orbitals
- `l = 1` → p orbitals
- `l = 2` → d orbitals
- `l = 3` → f orbitals

### Magnetic Quantum Number (`m`)

Controls phase structure and orbital circulation.

Changing `m` affects:

- Angular momentum
- Phase winding
- Probability flow around the orbital axis

---

# What You Can Observe

As the simulation runs you can directly see:

- Orbitals grow as `n` increases
- Shapes change as `l` changes
- Phase structure and circulation emerge as `m` becomes non-zero
- Nodal regions appear and disappear
- Probability distributions evolve in real time

This turns the renderer into a small interactive laboratory for understanding hydrogen atom quantum mechanics.

---

# Quantum Flow

Unlike many orbital viewers that only display probability density, this project also visualizes a simplified form of quantum circulation.

For states with non-zero magnetic quantum number (`m ≠ 0`), an azimuthal flow field is introduced to illustrate how phase winding can lead to circulating probability currents.

The goal is educational and intuitive rather than a full numerical evaluation of the quantum mechanical probability current.

---

# Documentation

For detailed explanations of:

- Schrödinger equation derivations
- Hydrogenic wavefunctions
- Spherical harmonics
- Quantum numbers
- Probability density sampling
- Monte Carlo generation
- Probability current theory
- Quantum flow visualization
- Renderer architecture
- Mathematical implementation details

please see:

**Atom (1).pdf**

---

# Credits

Inspired by Kavan's atom simulation project:

**GitHub:** https://github.com/kavan010/Atoms

This project expands upon those ideas with mathematically grounded hydrogen-orbital visualization, interactive quantum-number controls, probability-density rendering, and simplified quantum-flow visualization.