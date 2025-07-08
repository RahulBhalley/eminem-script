![RapScript](https://github.com/user-attachments/assets/a461c1f8-bb3c-42bc-ba45-1f49755f312d)

A Python-based interpreter for RapScript, a programming language inspired by Eminem's rap style and hip-hop culture.

## 🎤 About RapScript

RapScript brings the rhythm and wordplay of rap music to programming. Every keyword is inspired by hip-hop terminology, making coding feel like dropping bars.

## 🚀 Quick Start

### Prerequisites
- Python 3.7+
- No external dependencies required

### Installation

#### Basic Setup
```bash
# Clone or download the interpreter
git clone https://github.com/RahulBhalley/rapscript
cd rapscript-interpreter

# Run the interpreter directly
python3 rapscript_interpreter.py
```

#### Command-Line Setup (macOS/Linux)

To use `rapscript` as a command-line tool:

**Method 1: System-wide installation (Recommended)**
```bash
# Make the script executable
chmod +x rapscript_interpreter.py

# Create a system-wide command (requires sudo)
sudo ln -sf "$(pwd)/rapscript_interpreter.py" /usr/local/bin/rapscript-py
echo '#!/bin/bash\npython3 /usr/local/bin/rapscript-py "$@"' | sudo tee /usr/local/bin/rapscript
sudo chmod +x /usr/local/bin/rapscript
```

**Method 2: User-specific installation**
```bash
# Create a bin directory in your home folder
mkdir -p ~/bin

# Create the rapscript command script
cat > ~/bin/rapscript << 'EOF'
#!/bin/bash
python3 /full/path/to/rapscript_interpreter.py "$@"
EOF

# Make it executable
chmod +x ~/bin/rapscript

# Add to PATH (for zsh - default on macOS)
echo 'export PATH="$HOME/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc

# For bash users, use ~/.bash_profile instead
# echo 'export PATH="$HOME/bin:$PATH"' >> ~/.bash_profile
# source ~/.bash_profile
```

**Verification**
```bash
# Test the installation
rapscript --help  # Should show usage or run example
which rapscript   # Should show the path to your script
```

### Your First RapScript Program

Create a file called `hello.rap`:
```rapscript
cypher {
    spit greeting = "Yo, what's good?"
    flow greeting
    
    spit age = 25
    battle (age > 18) {
        flow "You're an adult!"
    } defeat {
        flow "Still young!"
    }
}
```

Run it:
```bash
rapscript hello.rap
```

Or run directly with Python:
```bash
python3 rapscript_interpreter.py hello.rap
```

## 📚 Language Reference

### Variables
```rapscript
spit name = "Eminem"          // String
spit age = 51                 // Number
spit is_goat = real           // Boolean true
spit is_fake = fake           // Boolean false
spit nothing = void           // Null
```

### Functions
```rapscript
// Regular function
verse greet(name) {
    flow "What's up, " + name + "!"
    return "greeting sent"
}

// Main function (entry point)
cypher {
    greet("Marshall")
}
```

### Control Flow
```rapscript
// If-else statements
battle (condition) {
    flow "True block"
} defeat {
    flow "False block"
}

// Comparison operators
battle (age > 18) { /* adult */ }
battle (name == "Eminem") { /* is eminem */ }
```

### Built-in Functions
```rapscript
flow "Hello World"        // Print to console
spit input = listen()     // Read user input
```

### Arithmetic
```rapscript
spit sum = 10 + 5         // Addition
spit diff = 10 - 5        // Subtraction
spit product = 10 * 5     // Multiplication
spit quotient = 10 / 5    // Division
```

## 🎯 Features

### ✅ Implemented
- [x] Variable declarations with `spit`
- [x] Function definitions with `verse`
- [x] Main function with `cypher`
- [x] Conditional statements (`battle`/`defeat`)
- [x] Arithmetic operations
- [x] Comparison operators
- [x] String and number literals
- [x] Boolean values (`real`/`fake`)
- [x] Function calls with parameters
- [x] Return statements
- [x] Variable scoping
- [x] Built-in I/O functions (`flow`, `listen`)
- [x] Comments with `//`

### 🚧 Coming Soon
- [ ] Loops (`freestyle`)
- [ ] Arrays (`tracks`)
- [ ] Objects (`albums`)
- [ ] String methods (`amplify`, `chop`, `flip`)
- [ ] Error handling (`attempt`/`choke`)
- [ ] More built-in functions

## 🔧 Usage

### Running RapScript Files

#### Command Line (after setup)
```bash
# Run a RapScript file
rapscript mycode.rap

# Run multiple files
rapscript file1.rap file2.rap
```

#### Direct Python Execution
```bash
# Run with Python directly
python3 rapscript_interpreter.py mycode.rap

# Run without arguments to see example
python3 rapscript_interpreter.py
```

### Creating RapScript Files

RapScript files use the `.rap` extension:

```bash
# Create a simple program
cat > example.rap << 'EOF'
verse greet(name) {
    flow "What's up, " + name + "!"
    return "greeting sent"
}

cypher {
    spit artist = "Eminem"
    greet(artist)
    
    spit age = 51
    battle (age > 30) {
        flow "Veteran status!"
    } defeat {
        flow "Young talent!"
    }
}
EOF

# Run it
rapscript example.rap
```

### Interactive Development

```bash
# Create and test quickly
echo 'cypher { flow "Quick test!" }' > test.rap
rapscript test.rap

# Edit with your favorite editor
nano myprogram.rap
vim myprogram.rap
code myprogram.rap  # VS Code
```

## 📖 Examples

### Hello World
Create `hello.rap`:
```rapscript
cypher {
    flow "Hello, RapScript World!"
}
```
Run: `rapscript hello.rap`

### User Input
Create `input.rap`:
```rapscript
cypher {
    flow "What's your name?"
    spit name = listen()
    flow "Yo " + name + ", welcome to RapScript!"
}
```
Run: `rapscript input.rap`

### Math Operations
Create `math.rap`:
```rapscript
verse calculate(a, b) {
    spit sum = a + b
    spit product = a * b
    flow "Sum:", sum, "Product:", product
    return sum
}

cypher {
    spit result = calculate(10, 5)
    flow "Result:", result
}
```
Run: `rapscript math.rap`

### Conditional Logic
Create `conditions.rap`:
```rapscript
verse check_age(age) {
    battle (age >= 18) {
        flow "You can vote!"
    } defeat {
        flow "Too young to vote"
    }
}

cypher {
    check_age(25)
    check_age(16)
}
```
Run: `rapscript conditions.rap`

### Complex Example
Create `rap_battle.rap`:
```rapscript
verse battle_round(rapper1, rapper2, round) {
    flow "Round " + round + ": " + rapper1 + " vs " + rapper2
    
    // Simulate battle scoring
    spit score1 = round * 2
    spit score2 = round * 3
    
    battle (score1 > score2) {
        flow rapper1 + " takes round " + round + "!"
        return rapper1
    } defeat {
        flow rapper2 + " takes round " + round + "!"
        return rapper2
    }
}

cypher {
    flow "Welcome to the RapScript Battle!"
    flow "========================================="
    
    spit rapper1 = "Eminem"
    spit rapper2 = "Jay-Z"
    
    spit winner1 = battle_round(rapper1, rapper2, 1)
    spit winner2 = battle_round(rapper1, rapper2, 2)
    spit winner3 = battle_round(rapper1, rapper2, 3)
    
    flow "========================================="
    flow "Final winner: " + winner3
}
```
Run: `rapscript rap_battle.rap`

## 🛠️ Architecture

### Components
1. **Lexer** - Tokenizes RapScript source code
2. **Parser** - Builds Abstract Syntax Tree (AST)
3. **Interpreter** - Executes the AST with proper scoping

### Token Types
- Keywords: `spit`, `verse`, `cypher`, `flow`, `battle`, etc.
- Operators: `+`, `-`, `*`, `/`, `==`, `>`, `<`
- Literals: strings, numbers, booleans
- Identifiers: variable and function names

### AST Nodes
- `Program` - Root node containing all statements
- `VariableDeclaration` - Variable assignments
- `FunctionDeclaration` - Function definitions
- `If` - Conditional statements
- `BinaryOp` - Arithmetic and comparison operations
- `Literal` - Constant values
- `Identifier` - Variable references

## 🐛 Troubleshooting

### Common Issues

**Command not found: rapscript**
```bash
# Check if the command exists
which rapscript

# If not found, verify installation
ls -la /usr/local/bin/rapscript

# Or check your PATH
echo $PATH | grep -o ~/bin
```

**Permission denied**
```bash
# Make sure the script is executable
chmod +x rapscript_interpreter.py
chmod +x /usr/local/bin/rapscript
```

**File not found errors**
```bash
# Check if your .rap file exists
ls -la *.rap

# Use absolute path if needed
rapscript /full/path/to/your/file.rap
```

**Python version issues**
```bash
# Check Python version (needs 3.7+)
python3 --version

# If python3 doesn't work, try python
python --version
```

### Error Messages

The interpreter provides helpful error messages:

```
Error: File 'missing.rap' not found
Error: Unexpected character '!' at line 3
Error: Expected IDENTIFIER, got NUMBER at line 5
Error: Undefined variable 'unknown_var'
Error: Division by zero
```

## 🤝 Contributing

Want to add more features to RapScript? Here's how:

1. **Add Keywords**: Update the `keywords` dict in `Lexer`
2. **New Operators**: Add to `TokenType` enum and parsing logic
3. **Built-in Functions**: Add to `Interpreter.__init__()` 
4. **Language Features**: Extend the `Parser` and `Interpreter` classes

### Example: Adding a New Built-in Function
```python
def builtin_amplify(self, text):
    """Convert text to uppercase"""
    return str(text).upper()

# In Interpreter.__init__():
self.globals.define("amplify", self.builtin_amplify)
```

## 📝 Language Philosophy

RapScript follows these principles:
- **Rhythm**: Code should flow like rap bars
- **Wordplay**: Creative naming with hip-hop terminology
- **Authenticity**: Respect for hip-hop culture
- **Simplicity**: Easy to learn, hard to master

## 🎵 Fun Facts

- Every program starts with a `cypher` (the main function)
- Variables are "spit" into existence
- Functions are called "verses"
- Conditionals are "battles" between conditions
- Output is "flowing" to the console

## 📄 License

This project is open source. Feel free to use, modify, and distribute.

## 👥 Authors

- Created with love for hip-hop and programming
- Inspired by Eminem's lyrical genius

---

*"In RapScript, every program is a performance, every function is a verse, and every coder is a lyricist."*

## 🔗 Related Projects

- [Brainfuck](https://esolangs.org/wiki/Brainfuck) - Another esoteric programming language
- [LOLCODE](https://esolangs.org/wiki/LOLCODE) - Programming language based on internet memes
- [Shakespeare](https://esolangs.org/wiki/Shakespeare) - Programming language that looks like Shakespeare plays

---

**Keep spitting those bars! 🎤**
