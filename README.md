# Traveling Salesman Problem - Algorithms and Heuristics

This repository contains a C++ command-line application for experimenting with exact and heuristic approaches to the Traveling Salesman Problem (TSP). It was developed for the [Algorithm Design](https://sigarra.up.pt/feup/en/UCURR_GERAL.FICHA_UC_VIEW?pv_ocorrencia_id=520321) course.

The program loads a graph dataset, lets the user choose a TSP strategy from an interactive menu, and prints the resulting tour cost and execution time.

## Algorithms

| Option | Algorithm | Notes |
| --- | --- | --- |
| 1 | Backtracking | Exact solution. Intended only for small graphs because it has factorial complexity. |
| 2 | 2-approximation | Builds an MST with Prim's algorithm and traverses it in preorder. Requires geographical coordinates when graph edges are missing. |
| 3 | Nearest Neighbor | Greedy heuristic that repeatedly chooses the closest unvisited vertex. |
| 4 | Christofides-Serdyukov | Builds an MST, matches odd-degree vertices, creates an Eulerian circuit, and shortcuts it into a TSP tour. |
| 5 | Real World | Nearest-neighbor tour starting from a source vertex provided by the user. |

## Repository Structure

```text
.
├── Application.cpp/.h      # Dataset loading and TSP algorithms
├── Graph.cpp/.h            # Graph, vertex, and edge data structures
├── Menu.cpp/.h             # Interactive terminal menus
├── main.cpp                # Program entry point
├── CMakeLists.txt          # CMake build configuration
├── graphs/                 # CSV graph datasets included in this repository
├── docs/Doxyfile           # Doxygen configuration
└── docs/output/            # Generated Doxygen HTML/LaTeX output
```

## Requirements

- C++17-compatible compiler.
- CMake 3.28 or newer.
- Doxygen, optional, for regenerating documentation.

## Build

```bash
cmake -S . -B build
cmake --build build
```

The CMake target is named `DA2024_PRJ2_G85_`.

## Run

Run the executable from the build directory. The application uses paths relative to that working directory, such as `../graphs/tourism.csv`.

```bash
cd build
./DA2024_PRJ2_G85_
```

Then choose a graph and an algorithm from the interactive menu.

## Documentation

If Doxygen is installed, the CMake configuration defines a `Doxygen` target and generates documentation from `docs/Doxyfile`.

Generated documentation is available under:

- `docs/output/html/index.html`
- `docs/output/latex/`

## Authors

- Diogo Venade, up202207805
- Tiago Monteiro, up202108391
- Vasco Costa, up202109923
