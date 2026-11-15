# Example 3: .NET MAUI UI-thread exception

> Synthetic example for skill testing. Not a real incident.

## Prompt

Can you help diagnose this MAUI exception on Android?

```text
System.InvalidOperationException:
The application called an interface that was marshalled for a different thread.

   at Microsoft.Maui.Controls.BindableObject.SetValue(...)
   at Microsoft.Maui.Controls.Label.set_Text(String value)
   at FieldApp.ViewModels.SyncViewModel.OnSyncCompleted(String message)
   at FieldApp.Services.SyncService.<RunAsync>d__12.MoveNext()
```

Framework: .NET MAUI  
Target: Android  
OS: Android 13  
The exception occurs intermittently after a background synchronization completes.

## What a good analysis should do

- Identify a likely UI-thread affinity violation because a UI-bound property is updated from a background continuation.
- State that the stack trace suggests, but does not fully prove, the execution context at the update.
- Ask for the `OnSyncCompleted` implementation and how the sync completion callback is invoked.
- Recommend dispatching the UI update through the MAUI main-thread dispatcher, with correct lifecycle and cancellation handling.
- Warn against blindly posting repeated callbacks or introducing retry loops.
- Test sync completion while the page is visible, navigating away, app backgrounding, cancellation, and repeated sync operations.
