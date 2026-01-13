Bitwarden’s browser extension can fill both your login credentials and, if configured, your 2FA/TOTP “authentication information” directly into the site your browser is on.[1][2][3]

## Basic browser autofill flow

- Install and log into the Bitwarden browser extension, then unlock your vault.  
- Save a login item that includes:
  - Username and password.  
  - The site URL (URI) so Bitwarden can match it to the current tab.  
- On the site’s login page, use one of these fill methods:[1][2]
  - Press **Ctrl/Cmd + Shift + L** with the cursor in a login field to autofill the last‑used matching login.  
  - Click the Bitwarden toolbar icon and then click the matching entry to fill.  
  - Right‑click in a field → **Bitwarden → Autofill** (not available in Safari).[1][2]

## Inline and on‑page autofill options

- In the extension, go to **Settings → Autofill** to enable features such as:  
  - Inline menu icons that appear in username/password fields; clicking the Bitwarden icon there fills the matching login.[1][4]
  - **Autofill on page load**, which can automatically fill a login as soon as the page loads (configurable per item or as default).[1][5]

## Using Bitwarden for TOTP / 2FA codes

- Edit the login item in Bitwarden and add a TOTP secret (the OTP key/QR contents) so Bitwarden’s **integrated authenticator** can generate codes.[6][3]
- When you autofill the login from the browser extension:  
  - Bitwarden can autofill the TOTP code directly into the 2FA field in many cases, or  
  - Copies the TOTP code to your clipboard so you can paste it into the site’s prompt, depending on the autofill mode.[7][8][3]

## Tips for reliable matching

- Ensure each login item has the correct site URL in the **URI** field (for example, `https://example.com`), and use specific match rules if needed (host, exact, etc.).[1][6][9]
- If Bitwarden does not show the expected item, open the extension on that page, edit the item, and enable **Autofill and save** or adjust the URI so it matches the domain actually in your browser.[1][6]

If you say which browser you use (Chrome, Firefox, Edge, Safari), a browser‑specific click‑by‑click sequence can be outlined.

## Typical Bitwarden usage 

Suppose that I want to access Github. I will start a Chrome browser (trying not to run interference with Safari, Firefox and Edge) and type https://github.com/adriatic/AI-RAG- into the address (IRL) line. Most likely I will get to see this 

![[Pasted image 20260102210642.png|300]]
Image 1

To get closer to this specific PRB use case. my intent to go to Github is to change my password. So, by unlocking the Bitwarden I get to see:

![[Pasted image 20260102211637.png|300]]
Image 2

This is the standard Bitwarder UI supporting most of the standard functions (search for a specific data). In this example I would choose Github and click on the 

![[Pasted image 20260102212214.png|300]]
Image 3

*Note that in this example we did use just standard Bitwarden tool - no PRB participation at all.*

*Note also that Bitwarden extension, activate by my click to Fill button, entered my credentials*

*Question is the above Fill action done by the Bitwarden extension - interacting with the browser's DOM??* I think that the answer is yes!)

---

Now, I am presenting the Bitwarden standard method to change a password. Note that like a case before, this is the Bitwarden Extension's UI - it is not sufficiently easy to support a large number of password changes (like all passwords in Bitwarden vault suspicious of being corrupted)

I switched to the case of changing a password for my bank (Github UI is too messy)

![[Pasted image 20260103172322.png|300]]
Image 4

Green marker 1 indicates that the browser is pointing to the place I want to do some changes (note the small 2 at the edge of Bitwarden Icon) and that I am already authenticated - click on the Fill Button which sets the userId and password and the Vault presents most of its functions.

In order to change the password for **THIS** website, have to click on "three dots" UI (green marker 3) and the select Edit function (green marker 4). This last action results with

![[Pasted image 20260103174512.png|300]]
Image 5

Where the actual data is hidden to preserve the privacy. Click on the Save button results with the transactional change of the data that was rewritten in these fields.

