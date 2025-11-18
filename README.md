# Moment0

**A Computational Mechanics Calculator for Centroid and Moment of Inertia**

Moment0 is a desktop GUI application that calculates the centroid and area moment of inertia (MOI) for various geometric shapes, including composite figures. It eliminates tedious manual calculations in engineering mechanics by providing an automated, user-friendly interface.

## Features

- **Rectangular Channel** - Calculate centroid and MOI for U-shaped cross-sections
- **Rectangular Channel with Slot** - Support for rectangular, square, triangular, or circular slots
- **Composite Figures** - Combine multiple shapes (rectangles, triangles, circles, semicircles)
- **Triangular Shapes** - Direct calculations for triangular cross-sections
- **Custom Reference Axes** - Calculate MOI about x-axis, y-axis, or any arbitrary axis
- **Parallel Axes Theorem** - Automatic application for offset calculations

## Screenshots

*Application windows for different calculation modes*

| Main Screen | Feature Selection | Calculation Window |
|-------------|-------------------|-------------------|
| Splash screen with navigation | Shape type selector | Input coordinates and view results |

## Quick Start

### Prerequisites

- **Java Development Kit (JDK) 11** or higher
- **Maven 3.6+** (for building from source)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/IndrarajBiswas/Moment0.git
   cd Moment0
   ```

2. **Extract the source code**
   ```bash
   unzip Moment0.zip -d Moment0_extracted
   cd Moment0_extracted/GUI
   ```

3. **Build with Maven**
   ```bash
   mvn clean compile
   ```

4. **Run the application**
   ```bash
   mvn exec:java -Dexec.mainClass="GUI"
   ```

### Alternative: Direct Java Compilation

```bash
cd Moment0_extracted/GUI/src/main/java
javac *.java
java GUI
```

## Project Structure

```
Moment0/
├── README.md                    # This file
├── Moment0.zip                  # Source archive
├── Moment0_extracted/           # Extracted source code
│   └── GUI/                     # Maven project
│       ├── pom.xml              # Maven configuration
│       └── src/main/java/       # Java source files
│           ├── GUI.java                              # Main entry point
│           ├── Features.java                         # Feature selection
│           ├── CompositeFigure.java                  # Composite options
│           ├── Foursided.java                        # Rectangle calculations
│           ├── FoursidedTriangle.java                # Rectangle + Triangle
│           ├── FoursidedTrianglecircle.java          # + Circle
│           └── FoursidedTrianglecirclesemicircle.java # + Semicircle
├── Mechanics Report.pdf         # Technical documentation
├── CompMech.pptx               # Presentation slides
└── User Manual.webm            # Video tutorial
```

## How It Works

### Application Flow

1. **Launch** - Open the splash screen
2. **Select Feature** - Choose shape type (A, B, C, or D)
3. **Input Data** - Enter coordinates and dimensions
4. **Calculate** - Click buttons for Area, Centroid, or MOI
5. **View Results** - Results display in output fields

### Calculation Modes

#### A. Rectangular Channel
Decomposes U-shaped channels into three rectangles and applies composite formulas.

#### B. Rectangular Channel with Slot
Uses the subtraction method: calculates main shape minus slot shape.

#### C. Composite Figures
Four progressive complexity options:
- Four-sided only
- Four-sided + Triangle
- Four-sided + Triangle + Circle
- Four-sided + Triangle + Circle + Semicircle

#### D. Triangular Shapes
Direct centroid and MOI calculations for triangular cross-sections.

## Mathematical Background

### Core Formulas

**Centroid of Composite Shapes:**
```
Cx = (A₁×Cx₁ + A₂×Cx₂ + ... + Aₙ×Cxₙ) / (A₁ + A₂ + ... + Aₙ)
Cy = (A₁×Cy₁ + A₂×Cy₂ + ... + Aₙ×Cyₙ) / (A₁ + A₂ + ... + Aₙ)
```

**Rectangle MOI:**
```
Ixx = (b × h³) / 12
Iyy = (h × b³) / 12
```

**Triangle MOI (about centroidal axis):**
```
I = (b × h³) / 36
```

**Parallel Axes Theorem:**
```
I' = I + A × d²
```
Where: I' = MOI about arbitrary axis, I = centroidal MOI, A = area, d = distance

## Technologies

- **Java 11** - Programming language
- **Swing/AWT** - GUI framework
- **Maven** - Build and dependency management
- **Nimbus Look and Feel** - Modern UI appearance

## Documentation

- **[Mechanics Report.pdf](Mechanics%20Report.pdf)** - Comprehensive technical documentation with theory, algorithms, and derivations
- **[CompMech.pptx](CompMech.pptx)** - Presentation slides
- **[User Manual.webm](User%20Manual.webm)** - Video tutorial demonstrating application usage

## Usage Examples

### Example 1: Rectangle Centroid

```
Input:
  x1 = 0, x2 = 4
  y1 = 0, y4 = 3

Output:
  Area = 12 sq units
  Centroid = (2, 1.5)
  Ixx = 9 units⁴
  Iyy = 16 units⁴
```

### Example 2: Triangle MOI

```
Input:
  Vertices: (0,0), (6,0), (3,4)

Output:
  Centroid = (3, 1.33)
  I (centroidal) = bh³/36 = 6×4³/36 = 10.67 units⁴
```

## Development

### Building from Source

```bash
cd Moment0_extracted/GUI
mvn clean package
```

### Running Tests

```bash
mvn test
```

### Creating JAR

```bash
mvn package
java -jar target/GUI-1.0-SNAPSHOT.jar
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Authors

**Group 5** - Amrita School of Engineering, Amritapuri

Course: Computational Mechanics (19PHY104)
Year: 2019

## License

This project is available for educational purposes. See the project documentation for more details.

## Acknowledgments

- Amrita Vishwa Vidyapeetham, Amritapuri Campus
- Department of Physics, Computational Mechanics Course
- Course instructors and mentors

## Troubleshooting

### Common Issues

**Java version error:**
```bash
# Check Java version
java -version

# Should show version 11 or higher
```

**Maven not found:**
```bash
# Install Maven on Ubuntu/Debian
sudo apt install maven

# Or on macOS with Homebrew
brew install maven
```

**GUI not displaying:**
- Ensure you have a display server running (X11 on Linux)
- On headless systems, use X11 forwarding: `ssh -X user@host`

## Support

For questions or issues:
- Check the [Mechanics Report.pdf](Mechanics%20Report.pdf) for detailed documentation
- Watch the [User Manual.webm](User%20Manual.webm) video tutorial
- Open an issue on GitHub

---

**Moment0** - Making Engineering Mechanics Calculations Simple
