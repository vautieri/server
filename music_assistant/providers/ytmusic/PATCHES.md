# YouTube Music No-Premium Patches

Three patches applied to `__init__.py` to enable YouTube Music without Premium:

1. **Line 1065**: `return True` instead of `return stream_format["format_id"] == "141"` — bypasses Premium check
2. **Line 1029**: `"bestaudio/best"` instead of `"m4a/bestaudio"` — accepts any audio format
3. **Line 1020**: `["web_music", "mweb", "android_music"]` instead of `["web_music"]` — fallback player clients

Patch 4 (StopIteration fix) is no longer needed — upstream now uses walrus operator with tuple unpacking.

## To merge upstream updates:
```bash
git fetch upstream
git merge upstream/main
# Resolve any conflicts in __init__.py
```
