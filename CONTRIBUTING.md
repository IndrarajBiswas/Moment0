# Contributing to Moment0

Thank you for your interest in contributing to Moment0! This document provides guidelines and information for contributors.

## How to Contribute

### Reporting Bugs

If you find a bug, please open an issue with:

1. **Description** - Clear description of the bug
2. **Steps to Reproduce** - How to trigger the bug
3. **Expected Behavior** - What should happen
4. **Actual Behavior** - What actually happens
5. **Environment** - Java version, OS, etc.

### Suggesting Features

Feature requests are welcome! Please include:

1. **Description** - What feature you'd like
2. **Use Case** - Why this feature would be useful
3. **Proposed Solution** - How it might work (optional)

### Pull Requests

1. **Fork** the repository
2. **Create a branch** from `main`
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Make your changes**
4. **Test** your changes thoroughly
5. **Commit** with clear messages
   ```bash
   git commit -m "Add: description of your changes"
   ```
6. **Push** to your fork
   ```bash
   git push origin feature/your-feature-name
   ```
7. **Open a Pull Request**

## Development Setup

### Prerequisites

- JDK 11 or higher
- Maven 3.6+
- Git

### Setting Up Local Environment

```bash
# Clone your fork
git clone https://github.com/YOUR-USERNAME/Moment0.git
cd Moment0

# Extract source
unzip Moment0.zip -d Moment0_extracted
cd Moment0_extracted/GUI

# Build
mvn clean compile

# Run
mvn exec:java -Dexec.mainClass="GUI"
```

## Code Style Guidelines

### Java Code

- Use meaningful variable and method names
- Add comments for complex calculations
- Follow standard Java naming conventions:
  - Classes: `PascalCase`
  - Methods/Variables: `camelCase`
  - Constants: `UPPER_SNAKE_CASE`

### Example

```java
// Good
public double calculateCentroidX(double[] areas, double[] centroids) {
    double sumProduct = 0;
    double sumArea = 0;

    for (int i = 0; i < areas.length; i++) {
        sumProduct += areas[i] * centroids[i];
        sumArea += areas[i];
    }

    return sumProduct / sumArea;
}

// Avoid
public double calc(double[] a, double[] c) {
    double s1 = 0, s2 = 0;
    for (int i = 0; i < a.length; i++) {
        s1 += a[i] * c[i];
        s2 += a[i];
    }
    return s1 / s2;
}
```

### Documentation

- Document public methods with Javadoc
- Include formulas in comments where applicable
- Update README for new features

## Project Structure

```
GUI/
└── src/main/java/
    ├── GUI.java              # Entry point - DO NOT heavily modify
    ├── Features.java         # Navigation - extend carefully
    └── [Shape].java          # Calculation classes - main development area
```

### Where to Add New Features

- **New shape types**: Create a new class following existing patterns
- **New calculations**: Add methods to relevant shape classes
- **UI improvements**: Modify existing JFrame classes

## Testing

### Manual Testing

Before submitting:

1. Test all calculation modes
2. Verify mathematical accuracy
3. Check UI responsiveness
4. Test edge cases (zero values, negative numbers)

### Test Cases to Verify

```
Rectangle (4x3):
- Area = 12
- Centroid = (2, 1.5)
- Ixx = 9
- Iyy = 16

Equilateral Triangle (base=6, height=4):
- Centroid y = 1.33
- I (centroidal) = 10.67
```

## Commit Message Format

Use clear, descriptive commit messages:

```
Add: new semicircle calculation method
Fix: centroid calculation for negative coordinates
Update: README with installation instructions
Refactor: extract common calculation methods
```

## Areas for Contribution

### High Priority

- Add input validation for all fields
- Implement unit tests
- Create cross-platform installer
- Add visualization of shapes

### Medium Priority

- Support for more shape types
- Export results to PDF/CSV
- Dark mode UI theme
- Internationalization (i18n)

### Documentation

- Add more usage examples
- Create video tutorials
- Translate to other languages

## Questions?

If you have questions:

1. Check existing documentation
2. Look through closed issues
3. Open a new issue with the "question" label

## Code of Conduct

- Be respectful and inclusive
- Provide constructive feedback
- Help others learn and grow
- Focus on the best outcome for the project

---

Thank you for contributing to Moment0!
