# You lack the required entitlement to use this resource

## Fixing “You lack the required entitlement to use this resource” Error

When you start your FiveM server and see this message, it means your server does not have the proper license or asset entitlement from **Keymaster**. This usually happens if the server key is not linked to the account that owns the asset.

***

### ✅ Steps to Solve

1. **Check Your License Key**
   * Go to FiveM [Keymaster](https://keymaster.fivem.net/login?return_url=/) or [Portal](https://portal.cfx.re/).
   * Log in with the **account that owns the asset** (the one that purchased or claimed it).
   * Verify the server license key is created under this account.
2. **Make Sure Your Server Uses the Correct Key**
   * Open your server configuration (`server.cfg`).
   *   Find the line with your license key, for example:

       ```
       sv_licenseKey your_license_key_here
       ```
   * Confirm this key is the one from the correct Keymaster account.
3. **Move or Recreate the Key (if needed)**
   * If your server is running with a license key from a different account, you must create a new one under the **correct Keymaster account**.
   * Replace the old key in `server.cfg` with the new one.
4. **Restart the Server**
   * Stop your server completely.
   * Start it again using the correct license key.

***

### ⚠️ Common Mistakes to Avoid

* Using a license key from a different account than the one that owns the asset.
* Copying resources from another server without making sure your account has the entitlement.
* Forgetting to restart the server after changing the license key.
