# Example 2: iOS watchdog termination

> Synthetic example for skill testing. Not a real incident.

## Prompt

What does this iOS crash report suggest? The app exits after the user taps Sign In.

```text
Incident Identifier: 00000000-1111-2222-3333-444444444444
Hardware Model: iPhone15,2
Process: FieldApp [412]
Version: 5.8.0 (50800)
OS Version: iPhone OS 17.5

Exception Type: EXC_CRASH (SIGKILL)
Termination Reason: FRONTBOARD 0x8badf00d
Application Specific Information:
watchdog transgression: scene-update
```

The report excerpt does not include the full thread backtraces.

## What a good analysis should do

- Explain that `0x8badf00d` commonly indicates a watchdog termination, not a conventional application exception.
- Avoid claiming that the sign-in network request is definitely the cause.
- State that the supplied excerpt is insufficient to identify the blocking operation.
- Request the complete report, especially relevant thread backtraces and the termination details.
- Ask whether sign-in performs synchronous work on the main thread.
- Recommend measuring main-thread work and testing slow-network, timeout, and repeated sign-in scenarios.
