# Agent Instructions

> This file is mirrored across CLAUDE.md, AGENTS.md, and GEMINI.md so the same instructions load in any AI environment.

## Windows Command Execution

**CRITICAL: On this system, `run_command` starts an interactive cmd session. Use this pattern:**

1. **First call**: `run_command` with an empty or simple command to start the session (WaitMsBeforeAsync: 2000)
2. **Then**: Use `send_command_input` to send your actual commands (dir, python script.py, etc.)
3. **Check output**: Use `command_status` to read the results

**Example workflow:**
```
run_command → starts cmd.exe session
send_command_input with "dir\n" → executes directory listing
command_status → reads the output
```

**DO NOT** try to execute commands directly with run_command - they won't execute until you send them via send_command_input. 

