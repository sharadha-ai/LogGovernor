# Rule: Structured Logging & Severity Audit
Target Directory: @[folder_path]

Objectives:
1. Audit all logging statements and strictly enforce log levels:
   - ERROR: Reserve EXCLUSIVELY for unhandled exceptions (include stack trace).
   - WARN: Degradations or recoverable fallback paths.
   - INFO: High-level lifecycle transitions only (e.g., "Order Processed").
   - DEBUG: Granular details, payload counts, or loop diagnostics.

2. Convert raw string concatenations/f-strings into structured JSON extra fields:
   logger.info("Message", extra={"user_id": user_id, "status": status})

3. Strip redundant payload array dumps inside loops—log item counts or IDs instead.

4. Generate a file diff before applying changes.
