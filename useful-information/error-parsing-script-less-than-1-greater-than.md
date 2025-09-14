# Error parsing script <\1>

## Fixing “Error parsing script <\1>”

This error usually shows up when your script files are **corrupted** or your **server artifacts are outdated**.

***

### ✅ Why This Happens

* Script/resource files got corrupted during upload or transfer.
* Your server is running on **old/outdated artifacts**.
* Incomplete or broken files inside the resource.

***

### ✅ Steps to Solve

1. **Check for Corrupted Files**
   * Delete the resource that is giving the error.
   * Re-download a **fresh copy** from [**Keymaster**](https://keymaster.fivem.net/login?return_url=/) or your [portal](https://portal.cfx.re/).
   * Upload it again using **WinSCP** (avoid FileZilla).
2. **Update Your Server Artifacts**
   * Go to the FiveM Server Artifacts page (or Linux if you use Linux).
   * Download the [**latest recommended build**](https://runtime.fivem.net/artifacts/fivem/build_server_windows/master/).
   * Replace your current server artifacts with the new ones.
3. **Clear Cache**
   * Stop your server.
   * Delete the `cache` folder inside your server directory (not the `server.cfg`).
   * Restart your server so it rebuilds the cache.
4. **Restart the Server**
   * After updating artifacts and re-uploading files, restart your server to apply changes.

***

### ⚠️ Common Mistakes to Avoid

* Running scripts on old server artifacts.
* Uploading files with FileZilla (causes corruption).
* Forgetting to clear the cache after replacing resources or updating artifacts.
