## CRITICAL: File Editing on Windows

### If a file has multiple modifications, use the Write tool to rewrite it all at once.

### When editing, always re-read the file first

**Before editing files, always use cat -A (or equivalent) to verify exact whitespace characters (tabs vs spaces)**

### ⚠️ MANDATORY: Always Use Backslashes on Windows for File Paths

**When using Edit or MultiEdit tools on Windows, you MUST use backslashes (`\`) in file paths, NOT forward slashes (`/`).**


#### ❌ WRONG - Will cause errors:
```
Edit(file_path: "D:/repos/project/file.tsx", ...)
MultiEdit(file_path: "D:/repos/project/file.tsx", ...)
```

#### ✅ CORRECT - Always works:
```
Edit(file_path: "D:\repos\project\file.tsx", ...)
MultiEdit(file_path: "D:\repos\project\file.tsx", ...)
```

### When File Edit failed
**When File Edit failed output the error detail， if String to replace not found, use Write tool to rewrite file. if file to write not exsits then create a empty file first. if other problems edit failed ask for approval**

### Precision in String Replacement
**To prevent `String to replace not found` errors, when using the `Edit` tool:
1. Always copy the exact string from the `Read` tool output.
2. Do NOT attempt to reformat, re-indent, or "clean up" the `old_string`. 
3. If a large block is being replaced and you are unsure of its exact structure, use the `Write` tool to rewrite the entire file instead of using `Edit`.**
