# Metro Path Finder (C++)

A C++ metro route-finding project that models metro lines and stations, indexes stations using an AVL tree, and searches for a route between an origin and a destination. The program displays the stations included in a route and calculates a fare using values stored in the input files.

## Features

- **Metro-line representation:** Stores each metro line as a doubly linked sequence of stations, allowing forward and backward traversal.
- **AVL-tree station index:** Organizes station names in an AVL tree and stores multiple station entries for interchange stations.
- **Route search:** Explores forward and backward travel and considers line changes at interchange stations.
- **Route details:** Prints station names, their metro-line names, the number of stops, and the calculated fare.
- **File-based data:** Loads station names and fare values from text files.

## Tech Stack

- **Language:** C++
- **Data structures:** AVL Tree, Doubly Linked List, Queue, Vector
- **Concepts:** AVL rotations and balancing, station lookup, route exploration, file handling, object-oriented programming

## Project Structure

```text
.
├── Main.cpp
├── interface.h
├── blue.txt
├── green.txt
├── magenta.txt
├── orange.txt
├── red.txt
├── violet.txt
└── yellow.txt
```

- `Main.cpp` — loads the metro-line files, builds the station index, and runs the route-finding test.
- `interface.h` — defines the metro stop, metro line, AVL tree, trip, path, and path finder classes.
- `*.txt` — contains station names and fare values for each metro line.

## How It Works

1. **Load metro lines:** Each text file is read and its stations are stored in a doubly linked list.
2. **Build the AVL tree:** Stations are inserted into an AVL tree. When a station appears on multiple lines, the AVL node stores references to the corresponding station instances.
3. **Search for a route:** The path finder explores stations in both directions and uses interchange stations to consider changing lines.
4. **Reconstruct the path:** Once the destination is found, the program traces the trip history to assemble the route.
5. **Display the result:** The program prints station and line details, the number of stops, and the calculated fare.

## Build and Run

### Prerequisites

- A C++ compiler supporting C++11 or later, such as `g++`.
- All source and data files in the same directory, unless you update the file paths in the code.

### Compile

```bash
g++ Main.cpp -o metro_path_finder
```

### Run

Linux/macOS:

```bash
./metro_path_finder
```

Windows:

```bash
metro_path_finder.exe
```

Run the executable from the directory containing the `.txt` data files, because the program loads them by filename.

## Example

The current test in `Main.cpp` searches for a route from **Central Secretariat** to **Botanical Garden**. The route and fare are generated from the supplied station data.

## Data Format

Each text file contains one station per line, with the station name followed by a numeric fare value, separated by spaces. For example:

```text
Dwarka Sec-21 0
Dwarka Sec-8 10
Dwarka Sec-9 20
```

Keep station names and fare values in the format expected by the parser in `interface.h`.

## Key Learning Outcomes

- Implementing AVL tree rotations and balancing.
- Representing ordered metro stations with a doubly linked list.
- Handling interchange stations shared by multiple metro lines.
- Reading structured data from text files.
- Combining data structures for route exploration and fare calculation.

## Future Improvements

- Add an interactive prompt for entering origin and destination stations.
- Improve route search to reliably return the shortest route and avoid repeated exploration.
- Add input validation and clearer errors for malformed data files.
- Improve memory management with smart pointers and automatic cleanup.
- Add automated tests for routes, interchanges, and invalid station names.

