# Example 1: Android Java NullPointerException

> Synthetic example for skill testing. Not a real incident.

## Prompt

Please analyze this Android crash. It happens when the user opens the order details screen.

```text
FATAL EXCEPTION: main
Process: com.example.fieldapp, PID: 18422
java.lang.NullPointerException: Attempt to invoke virtual method
'java.lang.String com.example.fieldapp.data.Order.getCustomerName()'
on a null object reference
    at com.example.fieldapp.ui.OrderDetailsActivity.bindHeader(OrderDetailsActivity.kt:84)
    at com.example.fieldapp.ui.OrderDetailsActivity.onCreate(OrderDetailsActivity.kt:42)
    at android.app.Activity.performCreate(Activity.java:9000)
    at android.app.Activity.performCreate(Activity.java:8978)
```

App version: 2.4.1 (20401)  
Android: 14  
Device: Pixel 7  
Frequency: 3 reports from 2 devices

## What a good analysis should do

- Classify this as an unhandled Java/Kotlin null dereference on the main thread.
- Identify `bindHeader` line 84 as the first relevant application frame.
- Explain that the exception identifies the null receiver of `Order.getCustomerName()`. That receiver is an `Order`. Do not treat every other object in the expression at line 84 as null. A view, binding, view model, or other call on that line is not implicated unless the message or the source shows it.
- Avoid assuming why that `Order` is null. Possible causes include missing navigation data, a failed lookup, asynchronous loading order, or unexpected saved state.
- Ask for the code around line 84 and the code that supplies/loads the `Order`.
- Recommend tests for missing order data, delayed loading, and process recreation if relevant.
- Do not claim that adding a null check alone fixes the underlying data-flow problem.
