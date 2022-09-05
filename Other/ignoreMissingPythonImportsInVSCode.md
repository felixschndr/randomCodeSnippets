## Purpose

I want to ignore missing python imports in Microsoft VScode.


## Code

Add
```json
    "python.analysis.diagnosticSeverityOverrides": {
        "reportMissingImports": "none"
    }
```
to `settings.json`.
