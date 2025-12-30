# Calculator Application

A fully functional GUI calculator built with Python's Tkinter library, featuring both basic arithmetic operations and advanced scientific functions.

## Features

### Basic Operations
- **Arithmetic**: Addition (+), Subtraction (-), Multiplication (*), Division (/)
- **Clear Function**: Clear the current display (C)
- **Equals**: Evaluate expressions (=)

### Scientific Functions
- **Trigonometric Functions**: sin, cos, tan (operate in degrees)
- **Exponents**: Square (^2), Power of 10 (10^x)
- **Logarithms**: Base 10 logarithm (log(x))
- **Reciprocal**: 1/x
- **Factorial**: x!
- **Square Root**: sqrt

### User Interface
- Clean, grid-based layout
- Large, readable display area
- Color-coded button design
- Responsive button feedback
- Error handling for invalid operations

## Screenshot

```
┌─────────────────────────────────────┐
│            Calculator               │
├─────────────────────────────────────┤
│              123.45                 │
├─────────────────────────────────────┤
│ [sin] [cos] [tan] [^2]  [10^x]     │
│ [ 7 ] [ 8 ] [ 9 ] [ / ] [log(x)]   │
│ [ 4 ] [ 5 ] [ 6 ] [ * ] [ 1/x ]    │
│ [ 1 ] [ 2 ] [ 3 ] [ - ] [ x! ]     │
│ [ 0 ] [ C ] [ = ] [ + ] [ sqrt ]   │
└─────────────────────────────────────┘
```

## Installation

### Prerequisites
- Python 3.6 or higher
- Tkinter (usually included with Python)

### Running the Calculator
1. **Clone or download** the calculator.py file
2. **Open a terminal** in the directory containing the file
3. **Run the application**:
   ```bash
   python calculator.py
   ```

## How to Use

### Basic Calculations
1. Enter numbers using the number buttons (0-9)
2. Select an operation (+, -, *, /)
3. Press `=` to calculate the result

### Scientific Calculations
1. Enter a number
2. Press the desired scientific function button
   - Example: Enter `45`, then press `sin` to calculate sine of 45 degrees
   - Example: Enter `4`, then press `x!` to calculate factorial of 4 (24)

### Clearing the Display
- Press `C` to clear the current input
- Errors automatically clear when you enter new input

## Code Structure

```python
calculator.py
├── Calculator class
│   ├── __init__()        # Initialize GUI and variables
│   ├── create_buttons()  # Create and arrange all buttons
│   └── click()          # Handle all button press events
└── Main execution
    └── Create Tkinter root window and run application
```

### Key Components
1. **Tkinter Window**: 400x500 pixel fixed-size window
2. **Entry Widget**: Display area for numbers and results
3. **Button Grid**: 5x5 grid of functional buttons
4. **Event Handling**: Lambda functions for button commands
5. **Error Handling**: Try-except blocks for safe calculations

## Technical Details

### Dependencies
- **tkinter**: GUI framework (standard library)
- **math**: Mathematical functions (standard library)

### Mathematical Functions Used
- `math.sin()`, `math.cos()`, `math.tan()`: Trigonometric functions
- `math.radians()`: Degree to radian conversion
- `math.log10()`: Base 10 logarithm
- `math.sqrt()`: Square root
- `math.factorial()`: Factorial calculation

### Error Handling
The calculator includes comprehensive error handling for:
- Division by zero
- Invalid mathematical operations
- Non-numeric inputs for scientific functions
- Empty display evaluations

## Future Enhancements

### Planned Features
1. **Keyboard Support**: Type directly using keyboard
2. **Memory Functions**: M+, M-, MR, MC buttons
3. **History Display**: View previous calculations
4. **Theme Options**: Light/dark mode toggle
5. **Additional Functions**: 
   - Inverse trigonometric functions
   - Logarithm with custom base
   - Constants (π, e)
   - Percentage calculations

### Code Improvements
1. **Modular Design**: Separate button creation from event handling
2. **Unit Tests**: Test each mathematical function
3. **Configuration File**: Customize colors and layout
4. **Internationalization**: Support for multiple languages

## Troubleshooting

### Common Issues
1. **Buttons don't appear**: Ensure `create_buttons()` is called in `__init__()`
2. **Display too small**: Adjust `geometry()` and row/column configurations
3. **Functions don't work**: Check math module imports and function calls
4. **Window not responding**: Verify `mainloop()` is called at the end

### Solutions
- Update Python to latest version
- Ensure Tkinter is properly installed (usually included)
- Check for syntax errors in the code

## Development Notes

### Design Choices
1. **Grid Layout**: Chosen for consistent button alignment
2. **Fixed Window Size**: Prevents layout distortion
3. **Large Fonts**: Improves readability
4. **Immediate Execution**: Functions execute immediately (no = needed for scientific functions)

### Code Quality
- Clean, commented code
- Consistent naming conventions
- Modular function design
- Comprehensive error handling

## License

This calculator is available for educational and personal use. Feel free to modify and distribute with proper attribution.

## Contributing

Contributions are welcome! Feel free to:
1. Report bugs
2. Suggest new features
3. Submit pull requests
4. Improve documentation

## Contact

For questions or feedback about this calculator application, please create an issue in the repository or contact the developer directly.

---
