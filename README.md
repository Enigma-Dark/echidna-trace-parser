# echidna-trace-parser

A parser that converts echidna call traces into foundry PoC tests

## Echidna Trace Parser

**Echidna Trace Parser** is a Python script designed to parse Echidna traces and generate corresponding Solidity test functions. This tool simplifies the process of converting Echidna output into usable Solidity tests, making it easier to verify smart contracts.

## Features

- **Parse Echidna Call Traces**: Extracts function calls, parameters, delays, and 'from' addresses from Echidna traces.
- **Generate Solidity Test Functions**: Automatically creates Solidity test functions based on the parsed data.
- **User-Friendly Input**: Allows users to paste Echidna traces directly into the terminal.

## Prerequisites

- Python 3.x
- Basic familiarity with the command line

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/echidna-trace-parser.git
   cd echidna-trace-parser
   ```
2. **Download the Script**: Alternatively, download the script file directly and save it in a directory of your choice.

3. **Ensure Python is Installed**: You can check if Python is installed by running:

   ```bash
   python3 --version
   ```

   If it’s not installed, download and install it from [python.org](https://www.python.org).

## Running the Script from Anywhere

To run the Echidna Trace Parser from any directory in your terminal, follow these steps:

### 1. Make the Script Executable

If you're using macOS or Linux, you can make the script executable:

- Open your terminal.
- Navigate to the directory where the script is located:
  ```bash
  cd /path/to/your/directory
  ```
- Run the following command to make the script executable:
  ```bash
  chmod +x echidna_parser.py
  ```

### 2. Add the Script to Your PATH

To run the script from anywhere, you can add its directory to your system's PATH.

#### On macOS/Linux

- Open your terminal.
- Edit your shell configuration file (like `~/.bashrc`, `~/.bash_profile`, or `~/.zshrc`) and add the following line, replacing `/path/to/your/directory` with the actual path where your script is located:
  ```bash
  export PATH="$PATH:/path/to/your/directory"
  ```
- Save the file and run:
  ```bash
  source ~/.bashrc
  ```
  (or the corresponding file for your shell).

#### On Windows

1. Search for "Environment Variables" in the Start menu.
2. Click on "Edit the system environment variables".
3. In the System Properties window, click on "Environment Variables".
4. In the "System variables" section, find and select the `Path` variable, then click "Edit".
5. Click "New" and add the full path to the directory where your script is saved.
6. Click OK to save your changes.

## Usage

1. Open your terminal.
2. Run the script from anywhere:
   ```bash
   echidna_parser.py
   ```
   or if you haven’t made it executable:
   ```bash
   python3 echidna_parser.py
   ```

3. **Input your Echidna call trace**:
   - Paste your Echidna call trace directly into the terminal.
   - Press Enter twice to finish input.

4. **View the Generated Solidity Test Function**: The tool will output the generated Solidity test function to the terminal.

## Example

```plaintext
Paste your Echidna call trace below. Press Enter twice to finish:
Tester.function_name(param1, param2) from: 0x12345 Time delay: 5
*wait* Time delay: 3

Generated Foundry Test Function:

function test_replay() public {
    _setUpActor(0x12345);
    _delay(5);
    Tester.function_name(param1, param2);
    _delay(3);
}
```

## Contributing

Contributions are welcome! If you would like to contribute to this project, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and commit them.
4. Push your branch and submit a pull request.

## License

This project is **not open-source**.

## Contact

For any inquiries or feedback, feel free to reach out on the organization's Discord server.

```
