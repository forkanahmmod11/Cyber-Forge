# Authorized Activity & Log Audit

Analyzes logs/telemetry from systems the operator owns or is authorized to access.

Features:
- login/logout activity
- failed authentication indicators
- user/account changes
- privilege/role changes
- API access
- admin actions
- API-key changes
- session/activity frequency
- IP/user frequency
- suspicious-event indicators
- JSON reporting

Usage:
```bash
./cyberforge activity-audit ./logs/app.json
```

Input can be a JSON array, `{"events": [...]}`, or JSON Lines.
