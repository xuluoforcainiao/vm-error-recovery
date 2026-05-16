# Secure Workspace Error Recovery

Diagnose and guide users through QoderWork secure workspace startup errors with actionable recovery steps.

## Use Cases

- Secure workspace startup failures
- Connection or download errors
- Any secure workspace related error messages

## Diagnostic Procedure

### Step 1: Read Diagnostic File
```
~/.qoderwork/vm/boot-state.json
```

Contains status, error info, environment info, phase details.

### Step 2: Match Error Key
Match `error.errorKey` against recovery instructions.

### Step 3: Guide User
Use user's language, plain non-technical language.

## Error Categories

### Category A: Simple Retry
- Startup timeout -> Close resource-heavy apps, restart QoderWork
- Insufficient resources -> Free memory, retry
- Network issues -> Check connection, disable VPN/proxy

### Category B: Specific Actions Required
- Workspace files corrupted -> Settings > Secure Workspace > Clean Workspace
- Disk full -> Ensure at least 20 GB free
- Security software blocking -> Add QoderWork to allowlist
- Windows Hyper-V disabled -> Enable Hyper-V in Control Panel

### Category C: Cannot Be Fixed by User
- macOS too old (requires macOS 14+)
- Unknown error -> Guide to submit feedback

## Core Principles

1. **Never expose internal details**: No hvkit, VSOCK, HCS mentions
2. **Platform awareness**: darwin -> macOS instructions, windows -> Windows instructions
3. **Language match**: Respond in user's language
4. **Reassuring tone**: Frame as common, fixable issues
5. **Always offer escalation**: If unresolved, guide to feedback button

## Version

Current: v1.0.0
