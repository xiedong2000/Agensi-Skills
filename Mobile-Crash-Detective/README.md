# Mobile Crash Detective

**Version:** 0.1.1  
**Purpose:** Evidence-based crash and runtime failure analysis for Android, iOS, and .NET MAUI developers.

Mobile Crash Detective helps developers interpret Sentry events, stack traces, Android Logcat output, Apple crash reports, and managed runtime exceptions. It separates facts from hypotheses, ranks plausible causes, and recommends targeted investigation steps, potential fixes, and regression tests.

## Included

```text
Mobile-Crash-Detective/
├── README.md
├── skills/
│   └── mobile-crash-detective/
│       └── SKILL.md
├── examples/
│   ├── android-null-reference.md
│   ├── ios-watchdog-termination.md
│   └── maui-ui-thread-exception.md
└── shared/
    └── diagnostic-report-template.md
```

## Supported diagnostic inputs

- Android Logcat, Java/Kotlin exceptions, ANR excerpts, and native crash summaries.
- iOS crash report excerpts, exception types, termination reasons, and thread backtraces.
- .NET MAUI and .NET runtime exceptions, including inner exceptions and async stack traces.
- Sentry event details, breadcrumbs, tags, release/environment metadata, and stack traces.
- Relevant source snippets and reproduction steps.

## Design principles

1. Evidence before certainty.
2. Facts, inferences, and hypotheses are clearly distinguished.
3. No claim of reproduction or verification without actual evidence.
4. Platform and version context matters.
5. Ask for the smallest useful missing diagnostic artifact.
6. Protect credentials, personal data, and customer information.

## Try the examples

The `examples/` directory contains synthetic diagnostic scenarios. They are illustrative training and validation inputs, not real customer incidents. Use them to check whether the skill:
- identifies the platform and failure category,
- extracts the important evidence,
- avoids overclaiming a root cause,
- proposes targeted next steps,
- recommends meaningful regression tests.

## Limitations

Version 0.1.1 analyzes information supplied by the user. It does not automatically connect to Sentry, inspect a repository, run an app, symbolicate a crash report, or execute tests. Those capabilities require appropriate integrations and tools. Suggested fixes must be validated in the affected app and environment.

## Privacy

Remove access tokens, credentials, personal information, customer identifiers, and private URLs before sharing logs. Do not submit proprietary source code or production data unless you are authorized to do so and the destination is approved.

## Version history

- **0.1.1** — An Android null-dereference message identifies the named method or field receiver, not every object in the source expression.
- **0.1.0** — Initial cross-platform diagnostic workflow for Android, iOS, and .NET MAUI.
