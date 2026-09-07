Stage 1: REPL (MVP)
Objective: Build a minimal viable prototype. While most functions are initially stubs, the interactive user dialog loop is fully operational.
Requirements:
CLI Interface: The application must run as a Command-Line Interface.
Custom Prompt: The input prompt must clearly feature the VFS identifier.
Argument Parsing: Implement a basic parser that tokenizes input by whitespace into a command and its arguments.
Stub Commands: Implement dummy ls and cd commands that simply echo their command name and received arguments.
Termination: Implement a graceful exit command.
Interactive Demo: Showcase the prototype in interactive mode, demonstrating all implemented functionality, including edge cases and error handling.
Version Control: Save the result to the repository using a standardized, descriptive commit message.
<img width="991" height="104" alt="image" src="https://github.com/user-attachments/assets/971c2b4d-0129-4e91-9e6e-64c0d51e4e8d" />

Stage 2: Configuration & Bootstrapping
Objective: Introduce configurability via CLI arguments and implement a debug dump of all active parameters upon emulator startup.
Requirements:
CLI Arguments:
--vfs-path: Path to the physical VFS storage location.
--script-path: Path to the startup execution script.
Startup Script Execution: Executes commands sequentially, gracefully skipping malformed lines. It echoes both input and output to the console, simulating a real interactive user session.
Error Reporting: Clearly report any execution errors encountered while running the startup script.
conf-dump Command: Outputs the current emulator configuration in a structured key-value format.
Test Harness: Create native OS shell scripts that invoke the emulator to validate all supported CLI argument combinations.
Version Control: Save the result to the repository using a standardized commit.
<img width="521" height="342" alt="image" src="https://github.com/user-attachments/assets/2384535e-1f73-461c-826d-f4d4310049a4" />

Stage 3: Virtual File System (VFS) Integration
Objective: Wire up the in-memory Virtual File System.
Requirements:
In-Memory Operations: All file system operations must occur strictly in memory. Unpacking or physically modifying the source VFS data is prohibited (except for designated service commands).
VFS Source Format: The VFS is sourced from a JSON file. Binary payloads must be encoded in Base64 (or an equivalent safe format).
Topology Testing: Create OS-level test scripts to validate the emulator against various VFS structures (minimal setup, multi-file setups, and deep nesting of ≥ 3 directory levels).
Comprehensive Test Script: Create a master startup script to test all commands implemented in this and previous stages, covering standard flows, VFS interactions, and error boundaries.
Version Control: Save the result to the repository using a standardized commit.
<img width="490" height="351" alt="image" src="https://github.com/user-attachments/assets/65777c00-6082-4918-952a-5486482425ce" />

Stage 4: Core UNIX-like Commands
Objective: Implement foundational commands that mimic a standard UNIX-like shell environment.
Requirements:
Navigation & Listing: Implement full, functional logic for ls and cd.
Utility Commands: Implement rev (string reversal) and echo.
Comprehensive Test Script: Create a master startup script to validate all newly implemented commands, including VFS state interactions and error handling scenarios.
Version Control: Save the result to the repository using a standardized commit.
<img width="408" height="570" alt="image" src="https://github.com/user-attachments/assets/6aa95a92-e55d-47f3-bdc0-198b04f468ec" />

Stage 5: State-Mutating Commands
Objective: Support advanced commands that mutate the VFS state (with all modifications strictly confined to in-memory representation).
Requirements:
Mutation Commands: Implement rm (remove file/directory) and mkdir (make directory).
Comprehensive Test Script: Create a master startup script to validate all Stage 5 commands, ensuring robust VFS state transitions, edge-case handling, and proper error reporting.
Version Control: Save the result to the repository using a standardized commit.
<img width="554" height="569" alt="image" src="https://github.com/user-attachments/assets/4e42f1cc-87fb-45de-ad08-cabb11106822" />
