# Failed to verify protected resource

## Fixing “Failed to verify protected resource” Error

This error means that your resource files are corrupted or damaged. It often happens when files are uploaded incorrectly to your VPS or server.

***

### ✅ Why This Happens

* Using **FileZilla** to upload files — it sometimes breaks or corrupts protected files.
* Transferring files incorrectly to a VPS.
* Missing or incomplete resource files.

***

### ✅ Steps to Solve

1. **Stop Your Server**
   * Always stop the server before replacing files.
2. **Re-download the Resource**
   * Go to FiveM [Keymaster](https://keymaster.fivem.net/login?return_url=/) or your [portal](https://portal.cfx.re/).
   * Download a fresh copy of the resource that is failing.
3. **Use WinSCP (Not FileZilla)**
   * Upload the files again using **WinSCP** instead of FileZilla.
   * WinSCP handles protected files correctly and avoids corruption.
4. **Replace the Old Resource**
   * Delete the corrupted resource folder from your server.
   * Upload the new fresh copy in its place.
5. **Restart Your Server**
   * Start the server again after uploading the fresh resource.

***

### ⚠️ Common Mistakes to Avoid

* **Do not** use FileZilla for uploading FiveM protected resources.
* **Do not** overwrite a broken resource with a new one without deleting it first.
* Always download directly from **Keymaster or your portal** to avoid broken copies.
